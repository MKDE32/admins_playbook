# EXAMPLES
```
get-process
```
```
get-process -name *malicious*
```
```
get-process | sort cpu -descending |select -first 3 | -property id, processname, cpu
```















