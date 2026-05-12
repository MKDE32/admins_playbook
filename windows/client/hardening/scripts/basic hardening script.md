```
Set-ExecutionPolicy Bypass -Scope Process -Force
.\hardening.ps1
```


```powershell
# =========================================
# WINDOWS CLIENT HARDENING SCRIPT
# =========================================

Write-Host "Starting Windows Hardening..." -ForegroundColor Cyan

# =========================
# Run as Admin Check
# =========================
If (-NOT ([Security.Principal.WindowsPrincipal] [Security.Principal.WindowsIdentity]::GetCurrent()
).IsInRole([Security.Principal.WindowsBuiltInRole] "Administrator"))
{
    Write-Host "Run as Administrator required!" -ForegroundColor Red
    exit
}

# =========================
# SMBv1 deaktivieren
# =========================
Write-Host "[*] Disabling SMBv1..." -ForegroundColor Yellow
Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol -NoRestart -ErrorAction SilentlyContinue

# =========================
# LLMNR deaktivieren
# =========================
Write-Host "[*] Disabling LLMNR..." -ForegroundColor Yellow
New-Item -Path "HKLM:\Software\Policies\Microsoft\Windows NT\DNSClient" -Force | Out-Null
Set-ItemProperty -Path "HKLM:\Software\Policies\Microsoft\Windows NT\DNSClient" `
-Name EnableMulticast -Type DWord -Value 0

# =========================
# NetBIOS deaktivieren
# =========================
Write-Host "[*] Disabling NetBIOS..." -ForegroundColor Yellow
Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled=TRUE" |
ForEach-Object { $_.SetTcpipNetbios(2) | Out-Null }

# =========================
# WPAD / Auto Proxy aus
# =========================
Write-Host "[*] Disabling WPAD..." -ForegroundColor Yellow
Set-ItemProperty -Path "HKCU:\Software\Microsoft\Windows\CurrentVersion\Internet Settings" `
-AutoDetect -Name AutoDetect -Value 0 -ErrorAction SilentlyContinue

# =========================
# Print Spooler deaktivieren
# =========================
Write-Host "[*] Disabling Print Spooler..." -ForegroundColor Yellow
Stop-Service Spooler -Force -ErrorAction SilentlyContinue
Set-Service Spooler -StartupType Disabled

# =========================
# Remote Registry deaktivieren
# =========================
Write-Host "[*] Disabling Remote Registry..." -ForegroundColor Yellow
Stop-Service RemoteRegistry -Force -ErrorAction SilentlyContinue
Set-Service RemoteRegistry -StartupType Disabled

# =========================
# SSDP / UPnP deaktivieren
# =========================
Write-Host "[*] Disabling UPnP / SSDP..." -ForegroundColor Yellow
Stop-Service SSDPSRV -Force -ErrorAction SilentlyContinue
Set-Service SSDPSRV -StartupType Disabled

# =========================
# Remote Desktop deaktivieren
# =========================
Write-Host "[*] Disabling RDP..." -ForegroundColor Yellow
Set-ItemProperty -Path "HKLM:\System\CurrentControlSet\Control\Terminal Server" `
-Name fDenyTSConnections -Value 1

# =========================
# Autorun deaktivieren
# =========================
Write-Host "[*] Disabling Autorun..." -ForegroundColor Yellow
New-Item -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer" -Force | Out-Null
Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer" `
-Name NoDriveTypeAutoRun -Value 255

# =========================
# Windows Script Host deaktivieren
# =========================
Write-Host "[*] Disabling WSH..." -ForegroundColor Yellow
New-Item -Path "HKLM:\Software\Microsoft\Windows Script Host\Settings" -Force | Out-Null
Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows Script Host\Settings" `
-Name Enabled -Value 0

# =========================
# PowerShell v2 entfernen
# =========================
Write-Host "[*] Removing PowerShell v2..." -ForegroundColor Yellow
Disable-WindowsOptionalFeature -Online -FeatureName MicrosoftWindowsPowerShellV2Root -NoRestart -ErrorAction SilentlyContinue

# =========================
# SMB Signing aktivieren
# =========================
Write-Host "[*] Enabling SMB Signing..." -ForegroundColor Yellow
New-Item -Path "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters" -Force | Out-Null
Set-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Services\LanmanWorkstation\Parameters" `
-Name RequireSecuritySignature -Value 1

# =========================
# TLS 1.0 / 1.1 deaktivieren
# =========================
Write-Host "[*] Disabling TLS 1.0/1.1..." -ForegroundColor Yellow

$tlsPaths = @(
"HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client",
"HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client"
)

foreach ($p in $tlsPaths) {
    New-Item -Path $p -Force | Out-Null
    Set-ItemProperty -Path $p -Name Enabled -Value 0 -Type DWord
    Set-ItemProperty -Path $p -Name DisabledByDefault -Value 1 -Type DWord
}

# =========================
# SmartScreen aktivieren
# =========================
Write-Host "[*] Enabling SmartScreen..." -ForegroundColor Yellow
Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows\CurrentVersion\Explorer" `
-Name SmartScreenEnabled -Value "RequireAdmin"

# =========================
# Windows Firewall Hardening
# =========================
Write-Host "[*] Hardening Firewall..." -ForegroundColor Yellow
Set-NetFirewallProfile -Profile Domain,Public,Private -Enabled True
Set-NetFirewallProfile -Profile Public -DefaultInboundAction Block -DefaultOutboundAction Allow

# =========================
# Optional: IPv6 Tunnel deaktivieren (nicht IPv6 komplett)
# =========================
Write-Host "[*] Disabling IPv6 tunneling mechanisms..." -ForegroundColor Yellow
netsh interface teredo set state disabled | Out-Null
netsh interface 6to4 set state disabled | Out-Null
netsh interface isatap set state disabled | Out-Null

# =========================
# Finish
# =========================
Write-Host ""
Write-Host "=========================================" -ForegroundColor Green
Write-Host "HARDENING COMPLETE - REBOOT RECOMMENDED" -ForegroundColor Green
Write-Host "=========================================" -ForegroundColor Green
```
