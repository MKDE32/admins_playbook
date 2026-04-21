# WUSA.EXE CHEAT SHEET (Windows Update Standalone Installer)
# For Admins / IT / Security

--------------------------------------------
BASIC USAGE
--------------------------------------------

wusa.exe update.msu
-> Installs a Windows Update package (.msu)

wusa.exe update.msu /quiet
-> Silent installation (no UI)

wusa.exe update.msu /norestart
-> Install but do NOT reboot automatically

wusa.exe update.msu /warnrestart
-> Warn user before reboot

wusa.exe update.msu /promptrestart
-> Prompt user to restart system

wusa.exe update.msu /forcerestart
-> Forces reboot after installation

--------------------------------------------
UNINSTALL UPDATES
--------------------------------------------

wusa.exe /uninstall /kb:1234567
-> Uninstall a specific update by KB number

wusa.exe /uninstall /kb:1234567 /quiet
-> Silent uninstall

wusa.exe /uninstall /kb:1234567 /norestart
-> Uninstall without reboot

--------------------------------------------
LOGGING
--------------------------------------------

wusa.exe update.msu /log:install.log
-> Creates installation log file

--------------------------------------------
ADMIN DEPLOYMENT EXAMPLES
--------------------------------------------

wusa.exe update.msu /quiet /norestart /log:C:\Logs\update.log
-> Silent deployment with logging (common in enterprise)

wusa.exe /uninstall /kb:500xxxx /quiet /norestart
-> Silent removal in scripts

--------------------------------------------
IMPORTANT NOTES
--------------------------------------------

- Requires Administrator privileges
- Works only with .msu packages (not .cab or .exe updates)
- Some updates may force reboot regardless of /norestart
- Best used in scripts, SCCM, or manual offline patching
- For modern systems, Windows Update / DISM / winget may be preferred
