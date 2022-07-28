# File System

``
lsblk
gdisk

format storage:
mkfs.ext4 /dev/sdb1

// mount
mkdir /mnt/ext4;
mount /dev/sdb1 /mnt/ext4

mount | grep /dev/sdb1/
``

to ensure mount is saved even after reboot, go to `/etc/fstab/`

check fs type: `sudo blkid /dev/vdc`


## NFS
`/etc/exports`

exportfs -a 
exportfs -o

## LVM (Logical Volume Manager)
sudo yum install -y lvm2

Create physical volume:
pvcreate /dev/sdb

Create volume group
vgcreate caleston_vg /dev/sdb

lvcreate -L 1G -n vol1 caleston_vg

List all physical volume/volume group
`pvdisplay`
`vgdisplay` or `vgs`
`lvdisplay` or `lvs`

increase volume
lvresize -L +1G -n /dev/caleston_vg/vol1
resize2fs /dev/caleston_vg/vol1