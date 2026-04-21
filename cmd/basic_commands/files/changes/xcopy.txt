# XCOPY CHEAT SHEET (Windows)
# For Admins / IT / Security

--------------------------------------------
BASIC SYNTAX
--------------------------------------------

xcopy source destination [options]

Example:
xcopy C:\Data D:\Backup

--------------------------------------------
COMMON OPTIONS
--------------------------------------------

/S
-> Copies directories and subdirectories (except empty ones)

/E
-> Copies all subdirectories including empty ones

/I
-> Assumes destination is a directory (important for folders)

/Y
-> Suppresses overwrite confirmation prompts

/-Y
-> Forces confirmation before overwrite

/C
-> Continues copying even if errors occur

/H
-> Copies hidden and system files

/R
-> Overwrites read-only files

/D[:date]
-> Copies only files newer than given date

--------------------------------------------
ADMIN / BACKUP USE CASES
--------------------------------------------

Full backup (including empty folders):
xcopy C:\Data D:\Backup /E /H /C /I /Y

Incremental backup (only newer files):
xcopy C:\Data D:\Backup /D /E /H /C /I /Y

Mirror-like copy (not perfect sync, but close):
xcopy C:\Source D:\Dest /E /H /R /Y /I

--------------------------------------------
LOGGING (WORKAROUND)
--------------------------------------------

xcopy C:\Data D:\Backup /E /H /Y > backup.log

--------------------------------------------
SECURITY / ADMIN NOTES
--------------------------------------------

- Requires appropriate file permissions
- Can copy hidden/system files with /H
- Does NOT delete files in destination (not a true sync tool)
- For modern systems, ROBOCOPY is preferred
- Can be used in scripts, legacy environments, recovery tasks

--------------------------------------------
COMMON PITFALLS
--------------------------------------------

- Missing /I causes prompt when copying folders
- Without /E, empty directories are skipped
- Without /H, system files are ignored
- Not reliable for large enterprise sync tasks
