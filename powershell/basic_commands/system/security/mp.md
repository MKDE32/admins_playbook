Get all Defender preferences:
Get-MpPreference

---

## 🖥️ Check Defender Status

Get full Defender status:
Get-MpComputerStatus

---

## 🔐 Core Protection Status

Check if protection is enabled:
(Get-MpComputerStatus).AntivirusEnabled

(Get-MpComputerStatus).AntispywareEnabled

(Get-MpComputerStatus).RealTimeProtectionEnabled

---

## 📦 Signature & Engine Updates

Check signature status:
Get-MpComputerStatus | Select AntivirusSignatureVersion, AntivirusSignatureLastUpdated

Update virus definitions:
Update-MpSignature

---

## ☁️ Cloud Protection Settings

Check MAPS / cloud protection:
Get-MpPreference | Select MAPSReporting

Check sample submission setting:
Get-MpPreference | Select SubmitSamplesConsent

---

## 📁 Exclusions (Audit & Management)

View excluded paths:
Get-MpPreference | Select ExclusionPath

View excluded processes:
Get-MpPreference | Select ExclusionProcess

View excluded file extensions:
Get-MpPreference | Select ExclusionExtension

---

## ➕ Manage Exclusions (Use with care)

Add excluded path:
Add-MpPreference -ExclusionPath "C:\Temp"

Add excluded process:
Add-MpPreference -ExclusionProcess "app.exe"

Add excluded extension:
Add-MpPreference -ExclusionExtension ".log"

Remove excluded path:
Remove-MpPreference -ExclusionPath "C:\Temp"

---

## 🧠 Threat Detection & History

View active/past threats:
Get-MpThreat

Get detailed threat detection history:
Get-MpThreatDetection

---

## ⚙️ System Health Overview

Quick security status check:
Get-MpComputerStatus | Select AMServiceEnabled, AntispywareEnabled, AntivirusEnabled, RealTimeProtectionEnabled

---

## 🔄 Maintenance

Run quick scan:
Start-MpScan -ScanType QuickScan

Run full scan:
Start-MpScan -ScanType FullScan

Update signatures:
Update-MpSignature

---

## 🧾 Policy & Configuration Review

View full Defender configuration:
Get-MpPreference

Check key security settings:
Get-MpPreference | Select DisableRealtimeMonitoring, DisableBehaviorMonitoring, DisableIOAVProtection

---

## 🧠 Admin Notes

- Requires **Administrator PowerShell**
- Some settings are controlled by **Group Policy / Intune**
- Changes may be logged in Windows Event Logs
- Recommended for:
  - Endpoint security management
  - Compliance checks
  - Incident response support

---

## ⚡ Key Cmdlets Summary

- Get-MpPreference → configuration
- Get-MpComputerStatus → system status
- Get-MpThreatDetection → detection history
- Update-MpSignature → update definitions
- Start-MpScan → manual scans
- Add/Remove-MpPreference → exclusions management
