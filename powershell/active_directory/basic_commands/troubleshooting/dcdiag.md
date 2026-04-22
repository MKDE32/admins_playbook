########## DCDIAG CHEATSHEET (DOMAIN CONTROLLER HEALTH) ##########

# Basic usage
dcdiag
dcdiag /v                 # verbose output
dcdiag /q                 # only errors
dcdiag /e                 # test all DCs in forest
dcdiag /a                 # test all DCs in site
dcdiag /s:DCNAME          # test specific DC

# Common tests
dcdiag /test:DNS
dcdiag /test:Replications
dcdiag /test:Advertising
dcdiag /test:Services
dcdiag /test:NetLogons
dcdiag /test:FSMOCheck
dcdiag /test:Connectivity

# Run multiple tests
dcdiag /test:DNS /test:Replications

# Output to file
dcdiag /v > dcdiag_report.txt

# Credentials (if needed)
dcdiag /u:DOMAIN\User /p:Password

###############################################################

# Key tests explained

| Test           | Purpose                              |
|----------------|--------------------------------------|
| DNS            | Checks DNS health/config             |
| Replications   | Verifies AD replication              |
| Advertising    | DC is advertising roles/services     |
| Services       | Required services running            |
| NetLogons      | SYSVOL & NETLOGON shares             |
| FSMOCheck      | FSMO roles reachable                 |
| Connectivity   | Basic network connectivity           |

###############################################################

# Common issues & fixes

| Issue                  | Possible Cause            | Action                     |
|------------------------|---------------------------|----------------------------|
| DNS errors             | Wrong DNS config          | Point client to DC DNS     |
| Replication failures   | Network / DC offline      | Check repadmin /replsummary|
| SYSVOL not shared      | DFSR/FRS issue            | Check SYSVOL replication   |
| DC not advertising     | AD service issue          | Restart NTDS service       |
| Access denied          | Missing permissions       | Use domain admin account   |

###############################################################

# Related tools
repadmin /replsummary     # replication overview
repadmin /showrepl        # detailed replication status
nltest /dsgetdc:domain    # find domain controller

###############################################################
