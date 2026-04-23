# SHOW EXECUTIONPOLICY
```
Get-ExecutionPolicy
Get-ExecutionPolicy -list
```





# SET EXECUTIONPOLICY
## EXAMPLE
```
set-executionPolicy -executionpolicy remotesigned -scope process
```

## FLAGS
### EXECUTION POLICY
- `-executionpolicy restricted` doesnt allow scripts
- `-executionpolicy remotesigned` allows only local scripts
- `-executionpolicy undefined` uses other places to look for the rules, in most cases it behaves like `restricted`
- `-executionpolicy bypass` bypasses the policy

### SKOPE
- `-scope machine policy` gpo
- `-scope user policy` gpo
- `-scope process policy`
- `-scope currentuser policy`
- `-scope localmachine policy`









