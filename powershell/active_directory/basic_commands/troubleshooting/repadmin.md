########## REPADMIN CHEATSHEET (AD REPLICATION) ##########

# Basic overview
repadmin /replsummary           # replication health summary
repadmin /showrepl              # detailed inbound replication per DC
repadmin /showrepl DCNAME       # specific DC

# Check replication partners
repadmin /showconn              # connection objects
repadmin /bridgeheads           # bridgehead servers

# Force replication
repadmin /syncall /AeD          # sync all partitions, all DCs
repadmin /syncall DCNAME /AeD   # sync specific DC

# Replication queue
repadmin /queue                 # pending replication operations

# Check failures
repadmin /failcache             # recent replication failures

# Metadata & objects
repadmin /showobjmeta DCNAME "DN"   # object metadata
repadmin /showattr DCNAME "DN"      # object attributes

# Lingering objects (advanced)
repadmin /removelingeringobjects DCNAME SOURCEDC "NC"

# Output to file
repadmin /replsummary > repl_report.txt

###########################################################

# Key commands explained

| Command            | Purpose                              |
|--------------------|--------------------------------------|
| /replsummary       | Forest-wide replication status       |
| /showrepl          | Detailed per-DC replication          |
| /syncall           | Force replication                    |
| /queue             | Check backlog                        |
| /failcache         | Show recent failures                 |
| /showconn          | Connection topology                  |
| /showobjmeta       | Object change history                |

###########################################################

# Common issues & fixes

| Issue                    | Possible Cause           | Action                          |
|--------------------------|--------------------------|----------------------------------|
| High fails in summary    | Network / DNS            | Check connectivity & DNS        |
| Last success long ago    | Replication stuck        | Run /syncall, check errors      |
| Access denied            | Permissions              | Use Domain Admin                |
| Lingering objects        | Stale DC                 | Remove with /removelingeringobjects |
| Large queue              | Slow DC / bandwidth      | Investigate load/network        |

###########################################################

# Useful flags

| Flag | Meaning                                  |
|------|------------------------------------------|
| /A   | All naming contexts                      |
| /e   | Enterprise (all sites)                   |
| /d   | Identify servers by DN                   |
| /q   | Quiet (errors only, limited support)     |

###########################################################

# Related tools
dcdiag                      # DC health check
nltest /dsgetdc:domain      # locate DC
Get-ADReplicationPartnerMetadata  # PowerShell alternative

###########################################################
