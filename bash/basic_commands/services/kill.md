# EXAMPLE
```
kill PID PID PID
```



# FLAGS
## SIGNALS

`kill`,      |   `kill -15`  |            |   SIGTERM  |  shut down  
             |   `kill -2`   |  `CTRL-C`  |   SIGINT   |  shut down foreground  
`kill -KILL` |   `kill -9`   |            |   SIGKILL  |  instant killing  
`kill -TSTP` |               |   `CTRL-Z` |   SIGTSTP  |  pause  
`kill -CONT` |               |            |   SIGCONT  |  continue

