# BASIC USAGE
--------------------------------------------

net view
-> Lists computers in the current domain or network

net view /domain
-> Lists available domains

net view /domain:<DOMAIN>
-> Lists computers in a specific domain

net view \\<computername>
-> Shows shared resources on a specific host

--------------------------------------------
# MOST IMPORTANT USE CASES
--------------------------------------------

net view
-> Quick network discovery (workgroup/domain machines)

net view /domain
-> Identify domain structure

net view /domain:WORKGROUP
-> Enumerate workgroup devices

net view \\TARGET-PC
-> Check shared folders on target system

net view \\192.168.1.10
-> Check shares via IP address

