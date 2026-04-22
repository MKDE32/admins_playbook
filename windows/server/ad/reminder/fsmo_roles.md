########## FSMO ROLES CHEATSHEET (ACTIVE DIRECTORY) ##########

# What are FSMO roles?
Flexible Single Master Operations roles in Active Directory that handle special tasks to avoid conflicts.

#############################################################

| Role                         | Scope        | Purpose (short)                         | Key Impact |
|------------------------------|--------------|------------------------------------------|------------|
| Schema Master               | Forest       | Controls AD schema changes              | Forest-wide structure updates |
| Domain Naming Master        | Forest       | Manages adding/removing domains         | Forest topology changes |
| RID Master                  | Domain       | Issues RID pools for object SIDs        | Unique object IDs |
| PDC Emulator                | Domain       | Time sync, password changes, legacy ops | Most critical for logons |
| Infrastructure Master       | Domain       | Updates cross-domain references         | Object consistency |

#############################################################

# FSMO role locations

| Role type | Number | Scope   |
|----------|--------|---------|
| Forest   | 2      | Forest-wide |
| Domain   | 3 per domain | Domain-wide |

#############################################################

# Check FSMO roles (PowerShell alternative)
Get-ADForest | Select-Object SchemaMaster, DomainNamingMaster
Get-ADDomain | Select-Object PDCEmulator, RIDMaster, InfrastructureMaster

#############################################################

# Classic command (legacy)
netdom query fsmo


# Important notes

- PDC Emulator = most important role in practice
- RID Master = prevents duplicate SIDs
- Schema Master = rarely used (only upgrades)
- If FSMO fails → domain operations may break



