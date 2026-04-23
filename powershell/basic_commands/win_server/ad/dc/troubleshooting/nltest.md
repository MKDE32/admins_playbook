# Basic domain / DC discovery
```
nltest /dsgetdc:DOMAIN              # find a domain controller
nltest /dsgetdc:DOMAIN /force       # force rediscovery
nltest /dsgetdc:DOMAIN /gc          # find global catalog
```

# Current domain info
```
nltest /dsgetdc:                    # get DC for current domain
nltest /dclist:DOMAIN               # list all DCs in domain
nltest /dcname:DOMAIN               # get primary DC name
```

# Secure channel (trust between client & DC)
```
nltest /sc_query:DOMAIN             # check secure channel status
nltest /sc_verify:DOMAIN            # verify secure channel
nltest /sc_reset:DOMAIN             # reset secure channel
```

# Trust relationships
```
nltest /domain_trusts               # list domain trusts
nltest /trusted_domains            # trusted domains
```

# Logon / authentication
```
nltest /user:USERNAME               # show user info
nltest /logon_query                 # logon status
```

# Force DC locator cache refresh
```
nltest /dsgetdc:DOMAIN /force
```

# Output debug info
```
nltest /dbflag:0x2080ffff           # enable verbose logging (advanced)
```

# Key commands explained

| Command              | Purpose                              |
|----------------------|--------------------------------------|
| /dsgetdc             | Locate a domain controller           |
| /dclist              | List all DCs                         |
| /sc_query            | Check secure channel                 |
| /sc_verify           | Verify trust with DC                 |
| /sc_reset            | Repair secure channel                |
| /domain_trusts       | Show trust relationships             |
| /dcname              | Show primary DC                      |




# Typical workflows

# Check DC connectivity
```
nltest /dsgetdc:DOMAIN
```

# Fix trust (client issues)
```
nltest /sc_verify:DOMAIN
nltest /sc_reset:DOMAIN
```

# List all DCs
```
nltest /dclist:DOMAIN
```
