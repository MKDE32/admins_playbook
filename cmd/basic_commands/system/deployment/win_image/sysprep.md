
BASIC USAGE
--------------------------------------------

sysprep
-> Opens GUI

sysprep /oobe
-> Boot into OOBE (Out-Of-Box Experience) on next start

sysprep /audit
-> Boot into Audit Mode on next start

--------------------------------------------
MOST IMPORTANT COMMANDS
--------------------------------------------

sysprep /oobe /reboot
-> Reboot and start OOBE

sysprep /oobe /shutdown
-> Prepare system and shut down (common for imaging)

sysprep /generalize /oobe /shutdown
-> REMOVE system-specific data (SID, drivers, logs)
-> Standard command for golden images

sysprep /audit /reboot
-> Enter Audit Mode for customization

--------------------------------------------
KEY FLAGS EXPLAINED
--------------------------------------------

/oobe
-> Starts Windows setup experience for new user

/audit
-> Boots into Audit Mode (admin mode, no OOBE)

/generalize
-> Removes unique system data (SID reset, logs, hardware info)

/shutdown
-> Shutdown after operation

/reboot
-> Reboot after operation

/quit
-> Close sysprep after running command

--------------------------------------------
UNATTENDED INSTALL (AUTOMATION)
--------------------------------------------

sysprep /generalize /oobe /shutdown /unattend:unattend.xml
-> Fully automated deployment using answer file

--------------------------------------------
IMPORTANT LIMITATIONS
--------------------------------------------

- Sysprep can only be run limited times (usually 3)
- Fails if certain Windows Store apps are installed/updated
- Must run as Administrator
- Not all systems support repeated generalization

--------------------------------------------
COMMON ERRORS / TROUBLESHOOTING
--------------------------------------------

- "Sysprep was not able to validate your Windows installation"
  -> Often caused by updated Store apps

- Check logs:
  C:\Windows\System32\Sysprep\Panther\setupact.log
  C:\Windows\System32\Sysprep\Panther\setuperr.log


IMPORTANT PATH
--------------------------------------------

C:\Windows\System32\Sysprep\
-> Contains sysprep executable and config files
