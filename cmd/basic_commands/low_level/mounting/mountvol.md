# BASIC COMMANDS

mountvol
-> List all volumes with GUIDs

mountvol C: /L
-> Show volume GUID for C: drive

mountvol C: <VolumeGUID>
-> Mount a volume to C: (advanced use)

mountvol C: /D
-> Remove mount point from C: drive

mountvol /R
-> Remove all orphaned volume mount points





# PRACTICAL ADMIN USE

mountvol
-> Identify hidden / system volumes

mountvol C: /L
-> Get exact volume identity (useful in troubleshooting)

mountvol /R
-> Clean broken or stale mount points


