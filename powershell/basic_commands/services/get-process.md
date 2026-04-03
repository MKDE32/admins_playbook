# EXAMPLES
```
get-process
```
```
get-process -name *malicious*
```
```
get-process | sort cpu -descending |select -first 3 -property id, processname, cpu
```

# SORTING
## PROPERTIES
`npm`
`pm`
`ws`
`cpu`
`id`
`name` or `processname`









