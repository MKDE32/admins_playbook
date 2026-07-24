########## EXAMPLES ##########
smbclient -N -L \\\\10.129.42.253
smbclient -L //172.16.10.5 -U INLANEFREIGHT\\vfrank

smbclient -U bob \\\\10.129.42.253\\users
smbclient //172.16.10.5/C$ -U vfrank



########## COMMANDS ##########
get password.txt



########## FLAGS ##########
smbversion
-m SMB2

list shares
-L

no auth
-N
