# OVERVIEW
Get a specific variable  
`$env:PATH`

List all environment variables  
`Get-ChildItem Env:`

Get variable with .NET  
`[System.Environment]::GetEnvironmentVariable("PATH")`





# SET
## CURRENT SESSION
Set a variable  
`$env:MY_VAR = "HelloWorld"`

Append to PATH  
`$env:PATH += ";C:\MyFolder"`

## PERSISTENT
current user  
`[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "User")`

machine  
`[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "Machine")`

process, same as $env  
`[System.Environment]::SetEnvironmentVariable("MY_VAR", "HelloWorld", "Process")`





# REMOVE
user variable  
`[System.Environment]::SetEnvironmentVariable("MY_VAR", $null, "User")`

machine variable  
`[System.Environment]::SetEnvironmentVariable("MY_VAR", $null, "Machine")`



# REFRESH
in Session, Reload PATH from registry (useful after persistent changes)
```
$env:PATH = [System.Environment]::GetEnvironmentVariable("PATH","Machine") + ";" +
            [System.Environment]::GetEnvironmentVariable("PATH","User")
```
