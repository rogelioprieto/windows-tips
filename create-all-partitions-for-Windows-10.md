# Delete "recovery partition" and create partitions for a "clean" Windows 10 installation 


## Problem:
You want to install a Windows 10 but you don't need the "recovery partition".

If you install Windows 10 with default parameteres, it will create a "recovery partition" unnecessary.

## Solution:
Create all others partitions except the "recovery partition".

## Important note:
If you execute these steps ALL DATA WILL BE DELETED in your hard drive or SDD drive.

## Steps:



1. STEP ONE. DELETE ALL PARTITIONS.
https://www.youtube.com/watch?v=N5v4kDzwVJc

◤ ◤ ◤ Commands: ◢ ◢ ◢

```bash
diskpart
list disk
select disk 0
list partition

select partition X
(Where x is the number of the recovery partition to be removed and unlocked its space. Be careful with the number of this partition, as   wrong number may get data wipes off.)

delete partition override 
```

2. STEP TWO. CREATE PARTIONS (except recovery partition)
<https://superuser.com/questions/1308324/create-efi-partition-before-installing-windows-10>

(BY ROGER)
```bash
clean
convert gpt

create partition efi size=100
format quick fs=fat32 label="System"


create partition primary size=51200
```







Sources:

<https://www.eassos.com/blog/how-to-create-esp-msr-partition-in-windows-10/>

<https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/create-partition-msr>

<https://www.eightforums.com/threads/recreating-microsoft-reserved-system-reserved-partition.69322/>

https://superuser.com/questions/1308324/create-efi-partition-before-installing-windows-10
