

# FLAGS
```
dcdiag /v                 # verbose output
dcdiag /q                 # only errors
dcdiag /e                 # test all DCs in forest
dcdiag /a                 # test all DCs in site
dcdiag /s:DCNAME          # test specific DC
```

# TESTS
```
dcdiag
dcdiag /test:DNS
dcdiag /test:Replications
dcdiag /test:Advertising
dcdiag /test:Services
dcdiag /test:NetLogons
dcdiag /test:FSMOCheck
dcdiag /test:Connectivity
```

# Run multiple tests
dcdiag /test:DNS /test:Replications

# Output to file
dcdiag /v > dcdiag_report.txt

# Credentials (if needed)
dcdiag /u:DOMAIN\User /p:Password

###############################################################

# INFO

| Test           | Purpose                              |
|----------------|--------------------------------------|
| DNS            | Checks DNS health/config             |
| Replications   | Verifies AD replication              |
| Advertising    | DC is advertising roles/services     |
| Services       | Required services running            |
| NetLogons      | SYSVOL & NETLOGON shares             |
| FSMOCheck      | FSMO roles reachable                 |
| Connectivity   | Basic network connectivity           |




