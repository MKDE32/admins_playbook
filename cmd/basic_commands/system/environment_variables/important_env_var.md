# WINDOWS ENVIRONMENT VARIABLES CHEATSHEET (ADMIN)

# Purpose: System administration, troubleshooting, deployment, scripting

--------------------------------------------
A
--------------------------------------------
ALLUSERSPROFILE
-> Common data for all users (C:\ProgramData)

APPDATA
-> Roaming profile data for current user

--------------------------------------------
C
--------------------------------------------
COMPUTERNAME
-> Hostname of the machine

COMSPEC
-> Path to cmd.exe

--------------------------------------------
H
--------------------------------------------
HOMEDRIVE
-> Drive of user profile (usually C:)

HOMEPATH
-> Path to user profile folder

--------------------------------------------
L
--------------------------------------------
LOCALAPPDATA
-> Local (non-roaming) app data

--------------------------------------------
O
--------------------------------------------
OS
-> Operating system name (Windows_NT)

--------------------------------------------
P
--------------------------------------------
PATH
-> Executable search paths (critical for admin scripts)

PATHEXT
-> File extensions treated as executable (.exe .bat .cmd)

PROCESSOR_ARCHITECTURE
-> CPU architecture (AMD64, x86)

PROCESSOR_IDENTIFIER
-> CPU details

PROCESSOR_LEVEL
-> CPU generation level

PROCESSOR_REVISION
-> CPU revision info

--------------------------------------------
S
--------------------------------------------
SYSTEMDRIVE
-> Windows system drive (C:)

SYSTEMROOT
-> Windows directory (C:\Windows)

--------------------------------------------
U
--------------------------------------------
USERNAME
-> Current logged-in user

USERPROFILE
-> Full path to user profile

--------------------------------------------
W
--------------------------------------------
WINDIR
-> Windows directory path

--------------------------------------------

ADMIN NOTES:
- PATH is the most critical variable in system troubleshooting
- SYSTEMROOT and WINDIR must never be modified carelessly
- USERPROFILE + APPDATA are key for per-user config issues
