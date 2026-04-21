
BASIC COMMANDS
--------------------------------------------

oobe\msoobe
-> Launch OOBE wizard manually

oobe\msoobe /f
-> Force OOBE to run again

oobe\msoobe /a
-> Activate Windows (legacy, not always used)

--------------------------------------------
BYPASS / SETUP SHORTCUTS
--------------------------------------------

`SHIFT + F10` to open the cmd, then:
```
oobe\bypassnro
```
-> Bypass network requirement (Windows 11 setup)
-> Adds "I don't have internet" option

--------------------------------------------
AUDIT MODE
--------------------------------------------

Ctrl + Shift + F3
-> Reboot into Audit Mode (no command needed)

# Or via command:
sysprep /audit /reboot

-> Boots into Audit Mode
-> Used for customization before user setup

--------------------------------------------
SYSPREP (RELATED TO OOBE)
--------------------------------------------

sysprep /oobe /reboot
-> Boot into OOBE on next start

sysprep /oobe /shutdown
-> Prepare system and shut down for imaging

sysprep /generalize /oobe /shutdown
-> Remove system-specific data (SID reset) + OOBE
-> Used for cloning / deployment

--------------------------------------------
USER CREATION (SETUP WORKAROUND)
--------------------------------------------

Shift + F10
-> Open CMD during OOBE

# Then:
net user admin password /add
net localgroup administrators admin /add

-> Create local admin account manually


IMPORTANT PATH
--------------------------------------------

C:\Windows\System32\oobe\
-> Contains OOBE-related executables
