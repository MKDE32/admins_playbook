# PowerShell Environment Variables Cheatsheet

## 📌 Accessing Environment Variables

```powershell
# Get a specific variable
$env:PATH

# List all environment variables
Get-ChildItem Env:

# Get variable with .NET
[System.Environment]::GetEnvironmentVariable("PATH")




Setting Environment Variables (Temporary - Current Session)
# Set a variable
$env:MY_VAR = "HelloWorld"

# Append to PATH
$env:PATH += ";C:\MyFolder"




persistent cu
[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "User")

pers machine
[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "Machine")

pers for process same as $env
[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "Process")







Removing Environment Variables
# Remove variable (User)
[System.Environment]::SetEnvironmentVariable("MY_VAR", $null, "User")

# Remove variable (Machine)
[System.Environment]::SetEnvironmentVariable("MY_VAR", $null, "Machine")




Refresh Environment Variables in Session
# Reload PATH from registry (useful after persistent changes)
$env:PATH = [System.Environment]::GetEnvironmentVariable("PATH","Machine") + ";" +
            [System.Environment]::GetEnvironmentVariable("PATH","User")




















