### Lecture Link 
- https://youtu.be/wz1S73yZ8fw?si=mvbhevrAEqXa9XD3
---
### Add new disk to your machine 
- After attach a new disk to machine if you have physical host you should reboot your machine to let BIOS detect the new disk attached. 
- If you are VM ware shutdown machine first.
- If you don't want to restart or shutdown machine you can use package called **s3g_utils.**
---
### fdisk 
- **`fdisk -l `** For all disks **or** **`fdisk -l /dev/sda`** To specify disk.
	This command give you more info about all the disks in your machine 
	- Number of sectors
	- Sector size 
	- Disk lable --> type [dos = MBR -> use BIOS] or [GPT -> use UEFI]
----
- `fdisk /dev/sda`
	- fdisk powerful tool to manage disk and partitions in disk so it deal with disk so don't use with partition like fdisk /dev/sda1 **WRONG**
	- If you use sda for first time `fdisk /dev/sda` will ask you to make it dos = MBR and suppose you have 4 partitions to create.
	- By default fdisk will ask you to start your partition after the first sector free [2048] = 128M cause disk reserve it. 
---
### partprobe
when you make any changes in disk or partition table in disk you should tell your kernal to read the MBR again cause kernal read MBR in two conditions [reboot - physical attach to disk].
`partprobe` this command will make kernal read MBR of all disks or specify 
`partprobe /dev/sda`

---
### mkfs 
- After creating partition you need to format it with file system we talk in Lecture 15
- mkfs is used with partitions so mkfs.extd /dev/sda **WRONG**
- `mkfs.ext4 /dev/sda1` Format this partiton with FS ext4
# continue https://youtu.be/wz1S73yZ8fw?si=PhU-sjin6i7ECMNF in 45:00