```
Start-Process powershell.exe -Verb RunAs -ArgumentList "-NoExit -ExecutionPolicy Bypass -File `"$PWD\hardening.ps1`""
```





```powershell
# Windows Hardening Script
# Zweck:
# - Netzwerkprofil auf "Öffentlich" setzen (fremdes Netzwerk)
# - IPv6 soweit praktikabel deaktivieren/absichern
# - UAC auf maximale Stufe setzen
# - Medien-Autoplay deaktivieren
# - Google DNS-over-HTTPS (DoH) systemweit konfigurieren
# - Klassisches DNS-Fallback vermeiden
# - Anzeige von Dateiendungen aktivieren
# - Ergebnisreport ausgeben
#
# Ausführung:
# 1. PowerShell als Administrator starten
# 2. Optional:
#    Set-ExecutionPolicy -Scope Process Bypass
# 3. Script ausführen
#
# Hinweis:
# Einige Änderungen benötigen einen Neustart.
# IPv6 wird von Windows intern teilweise vorausgesetzt.
# Daher wird hier IPv6 bevorzugt deaktiviert/gehärtet statt vollständig entfernt.

#Requires -RunAsAdministrator

$Results = [System.Collections.Generic.List[Object]]::new()

function Add-Result {
    param(
        [string]$Task,
        [string]$Status,
        [string]$Details
    )

    $Results.Add([PSCustomObject]@{
        Task    = $Task
        Status  = $Status
        Details = $Details
    })
}

function Run-Step {
    param(
        [string]$Name,
        [scriptblock]$Action
    )

    try {
        & $Action
        Add-Result -Task $Name -Status 'OK' -Details 'Erfolgreich'
    }
    catch {
        Add-Result -Task $Name -Status 'FEHLER' -Details $_.Exception.Message
    }
}

Write-Host ''
Write-Host '=== Windows Hardening Script ===' -ForegroundColor Cyan
Write-Host ''

# ------------------------------------------------------------
# 1. Netzwerkprofil auf Öffentlich setzen
# ------------------------------------------------------------
Run-Step 'Netzwerkprofil -> Öffentlich' {
    $profiles = Get-NetConnectionProfile

    foreach ($profile in $profiles) {
        Set-NetConnectionProfile -InterfaceIndex $profile.InterfaceIndex -NetworkCategory Public
    }
}

# ------------------------------------------------------------
# 2. Netzwerk-Erkennung und Freigaben reduzieren
# ------------------------------------------------------------
Run-Step 'Datei- und Druckerfreigabe deaktivieren' {
    Set-NetFirewallRule -DisplayGroup 'Datei- und Druckerfreigabe' -Enabled False -ErrorAction SilentlyContinue
}

Run-Step 'Netzwerkerkennung deaktivieren' {
    Set-NetFirewallRule -DisplayGroup 'Netzwerkerkennung' -Enabled False -ErrorAction SilentlyContinue
}

# ------------------------------------------------------------
# 3. IPv6 absichern / weitgehend deaktivieren
# ------------------------------------------------------------
Run-Step 'IPv6 Präferenz deaktivieren' {
    # 0x20 bevorzugt IPv4 gegenüber IPv6
    New-ItemProperty -Path 'HKLM:\SYSTEM\CurrentControlSet\Services\Tcpip6\Parameters' -Name 'DisabledComponents' -PropertyType DWord -Value 0x20 -Force | Out-Null
}

Run-Step 'IPv6 Bindings auf Adaptern deaktivieren' {
    $adapters = Get-NetAdapter | Where-Object { $_.Status -eq 'Up' }

    foreach ($adapter in $adapters) {
        Disable-NetAdapterBinding -Name $adapter.Name -ComponentID ms_tcpip6 -ErrorAction SilentlyContinue
    }
}

Run-Step 'Teredo deaktivieren' {
    netsh interface teredo set state disabled | Out-Null
}

Run-Step 'ISATAP deaktivieren' {
    netsh interface isatap set state disabled | Out-Null
}

Run-Step '6to4 deaktivieren' {
    netsh interface 6to4 set state disabled | Out-Null
}

# ------------------------------------------------------------
# 4. UAC maximale Sicherheitsstufe
# ------------------------------------------------------------
Run-Step 'UAC Maximum aktivieren' {

    $uacPath = 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System'

    Set-ItemProperty -Path $uacPath -Name 'EnableLUA' -Value 1
    Set-ItemProperty -Path $uacPath -Name 'ConsentPromptBehaviorAdmin' -Value 2
    Set-ItemProperty -Path $uacPath -Name 'PromptOnSecureDesktop' -Value 1
    Set-ItemProperty -Path $uacPath -Name 'ConsentPromptBehaviorUser' -Value 3
}

# ------------------------------------------------------------
# 5. Medien-Autoplay deaktivieren
# ------------------------------------------------------------
Run-Step 'Autoplay deaktivieren' {

    $explorerPath = 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Explorer\AutoplayHandlers'

    New-Item -Path $explorerPath -Force | Out-Null

    Set-ItemProperty -Path $explorerPath -Name 'DisableAutoplay' -Value 1

    $policyPath = 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer'

    New-Item -Path $policyPath -Force | Out-Null

    Set-ItemProperty -Path $policyPath -Name 'NoDriveTypeAutoRun' -Value 255
}

# ------------------------------------------------------------
# 6. Dateiendungen anzeigen
# ------------------------------------------------------------
Run-Step 'Dateiendungen anzeigen' {

    $advPath = 'HKCU:\Software\Microsoft\Windows\CurrentVersion\Explorer\Advanced'

    Set-ItemProperty -Path $advPath -Name 'HideFileExt' -Value 0
}

# ------------------------------------------------------------
# 7 + 8. Google DNS + DNS-over-HTTPS
# ------------------------------------------------------------

Run-Step 'Google DNS + DoH konfigurieren' {

    $dnsServers = @('8.8.8.8', '8.8.4.4')

    $adapters = @(Get-DnsClient | Where-Object {
        $_.InterfaceAlias -notmatch 'Loopback' -and
        $_.InterfaceOperationalStatus -eq 'Up'
    })

    foreach ($adapter in $adapters) {

        Set-DnsClientServerAddress `
            -InterfaceIndex $adapter.InterfaceIndex `
            -ServerAddresses $dnsServers
    }

    $dohPath = 'HKLM:\SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\DohWellKnownServers'

    New-Item -Path $dohPath -Force | Out-Null

    New-ItemProperty `
        -Path $dohPath `
        -Name '8.8.8.8' `
        -PropertyType String `
        -Value 'https://dns.google/dns-query' `
        -Force | Out-Null

    New-ItemProperty `
        -Path $dohPath `
        -Name '8.8.4.4' `
        -PropertyType String `
        -Value 'https://dns.google/dns-query' `
        -Force | Out-Null

    ipconfig /flushdns
}

# ------------------------------------------------------------
# 9. SMBv1 deaktivieren
# ------------------------------------------------------------
Run-Step 'SMBv1 deaktivieren' {
    Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol -NoRestart -ErrorAction SilentlyContinue | Out-Null
}

# ------------------------------------------------------------
# 10. Gastkonto deaktivieren
# ------------------------------------------------------------
Run-Step 'Gastkonto deaktivieren' {

    $guestAccounts = @('Guest','Gast')

    foreach ($account in $guestAccounts) {

        $exists = Get-LocalUser -Name $account -ErrorAction SilentlyContinue

        if ($exists) {
            Disable-LocalUser -Name $account
        }
    }
}

# ------------------------------------------------------------
# 11. SmartScreen aktivieren
# ------------------------------------------------------------
Run-Step 'SmartScreen aktivieren' {

    $ssPath = 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer'

    Set-ItemProperty -Path $ssPath -Name 'SmartScreenEnabled' -Value 'RequireAdmin'
}

# ------------------------------------------------------------
# 12. Explorer neu starten
# ------------------------------------------------------------
Run-Step 'Explorer neu starten' {
    Stop-Process -Name explorer -Force -ErrorAction SilentlyContinue
    Start-Process explorer.exe
}

# ------------------------------------------------------------
# Zusammenfassung
# ------------------------------------------------------------

Write-Host ''
Write-Host '=== Ergebnis ===' -ForegroundColor Cyan
Write-Host ''

$Results | Format-Table -AutoSize

Write-Host ''
Write-Host 'Hinweise:' -ForegroundColor Yellow
Write-Host '- Ein Neustart wird empfohlen.'
Write-Host '- Manche VPN-Clients oder Unternehmensnetzwerke können DoH überschreiben.'
Write-Host '- Einige Windows-Komponenten erwarten weiterhin IPv6-Unterstützung.'
Write-Host '- Prüfen: Einstellungen -> Netzwerk & Internet -> DNS-Serverzuweisung'
Write-Host ''

# Optional: Ergebnis als Datei speichern
$reportPath = "$env:USERPROFILE\Desktop\hardening_report.txt"

$Results | Out-File -FilePath $reportPath -Encoding UTF8

Write-Host "Report gespeichert unter: $reportPath" -ForegroundColor Green

```
