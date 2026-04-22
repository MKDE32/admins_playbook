# SHOW EXECUTIONPOLICY
```
Get-ExecutionPolicy
Get-ExecutionPolicy -list
```
- PS Ausführungsrichtlinie ansehen



# SET EXECUTIONPOLICY
```
Set-ExecutionPolicy Restricted
Set-ExecutionPolicy RemoteSigned
Set-ExecutionPolicy undefined
```
- Restricted - Can run only Microsoft signed Scripts
- RemoteSigned - Can run custom Scripts
- undefined



# BYPASS
```
Set-ExecutionPolicy Bypass -Scope Process
```
- Set the `PowerShell` execution policy to bypass for the current session



