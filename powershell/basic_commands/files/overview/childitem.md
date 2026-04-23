# EXAMPLES
```
get-childitem -Path *.txt | rename-item -NewName {$_.name -replace ".txt",".md"}

Get-Childitem –Path C:\Users\luser\ -File -Recurse -ErrorAction SilentlyContinue | where {($_.Name -like "*.txt")}
Get-Childitem –Path C:\Users\luser\ -File -Recurse -ErrorAction SilentlyContinue | where {($_.Name -like "*.txt" -or $_.Name -like "*.py" -or $_.Name -like "*.ps1" -or $_.Name -like "*.md" -or $_.Name -like "*.csv")}

Get-ChildItem -Path C:\Users\lusere\ -Filter "*.txt" -Recurse -File | sls "Password","credential","key"
Get-ChildItem -Recurse -Filter "*.txt" -File | Get-Content
```





# FLAGS
`-Path C:\Users\luser\`  
`-Recurse`  
`-File`  
`-Hidden`  
`-ErrorAction SilentlyContinue`  





# FILTERING
`| rename-item -NewName {$_.name -replace ".txt",".md"}`  
`| where {($_.Name -like "*.txt")}`  
`| where {($_.Name -like "*.txt" -or $_.Name -like "*.py" -or $_.Name -like "*.ps1" -or $_.Name -like "*.md" -or $_.Name -like "*.csv")}`  
`| sls "Password","credential","key"`  
`| Get-Content`





# CHAIN OPERATORS
`&&` ps will execute the next command inline if the current command completes properly.  
`||` ps will execute the following command inline if the current command fails.





# COMPARISON OPERATORS
`Like` matching wildcard expressions e.g., `'*password*'`  
`Contains` value matches exactly as specified  
`Equal to` exact matching, case sensitive  
`Match` regex matching  
`Not` matches if the property is blank or does not exist or matches `$False`  
