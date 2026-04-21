# ROBOCOPY CHEAT SHEET (Windows Admin / IT / Security)

# Tool: Robocopy (Robust File Copy)
# Purpose: Reliable file copy, backup, and directory sync for Windows systems


--------------------------------------------
BASIC SYNTAX
--------------------------------------------

robocopy <source> <destination> [files] [options]

Example:
robocopy C:\Data D:\Backup


--------------------------------------------
MOST IMPORTANT ADMIN EXAMPLES
--------------------------------------------

1) Basic folder backup
robocopy C:\Data D:\Backup /E

2) Full mirror backup (sync exactly)
robocopy C:\Data D:\Backup /MIR

3) Safe backup with restart support
robocopy C:\Data D:\Backup /E /Z

4) Fast backup with multiple threads
robocopy C:\Data D:\Backup /E /MT:16

5) Backup with logging (very common in IT)
robocopy C:\Data D:\Backup /E /LOG:C:\Logs\backup.log

6) Production-safe backup (retry + logging + restartable)
robocopy C:\Data D:\Backup /E /Z /R:3 /W:5 /LOG:C:\Logs\backup.log

7) Copy only newer files (incremental backup style)
robocopy C:\Data D:\Backup /E /XO


--------------------------------------------
COMMON ADMIN FLAGS
--------------------------------------------

/E
-> Copy all subdirectories including empty ones

/MIR
-> Mirror source to destination (WARNING: deletes extra files in target)

/Z
-> Restartable mode (safe for network drops)

/MT[:n]
-> Multi-threaded copy (default 8, max 128)

/R:n
-> Retry count on failure (default 1 million)

/W:n
-> Wait time between retries (seconds)

/LOG:file
-> Write output to log file

/LOG+:file
-> Append to log file

/NP
-> No progress display (clean logs)

/NFL
-> No file list (less output)

/NDL
-> No directory list (less output)

/XO
-> Exclude older files (only copy newer ones)

/XN
-> Exclude newer files

/XC
-> Exclude changed files

/XF
-> Exclude files

/XD
-> Exclude directories

/FFT
-> Tolerates FAT timestamp differences (useful for network drives)


--------------------------------------------
SECURITY / ADMIN NOTES
--------------------------------------------

- /MIR can delete files in destination (use carefully)
- /Z is important for unstable network copies
- /LOG is essential for audits and troubleshooting
- /MT significantly improves performance
- Always test scripts before production deployment
- Requires proper NTFS permissions
- Works best in scheduled tasks or deployment scripts


--------------------------------------------
COMMON REAL-WORLD USE CASES
--------------------------------------------

- System backups
- Server migrations
- User profile backups
- Network share synchronization
- Deployment pipelines
- Incident recovery copying
