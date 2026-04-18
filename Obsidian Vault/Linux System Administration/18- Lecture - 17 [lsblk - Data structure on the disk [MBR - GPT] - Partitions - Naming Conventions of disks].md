### Lecture Link 
 - https://youtu.be/eME7olWqPQs?si=6-xvKBkR2cBVUORG
---
### Data structure on the disk [MBR - GPT]
- **MBR**
	- Space = 512 byte 
	- Total Partition tables space = 64 byte 
	- Each Partition = 16 byte
	- Max Primary Partitions = 64/16 = 4 partitions
	- MBR is old it's used with **Boot Mode** [BIOS]
	- **Max Disk Size** = 2 TB
- **GPT**
	- Modern it's used with **Boot Mode** [UEFI]
	- **Max Disk Size** = 9.4 ZB (Zettabytes)
	- Max Primary Partitions = 128
---
### Partitions

![[Partitions Lecture 17.png]]

- In MBR the fourth partition can be devided to many logical partitions.
- If you have 2 partitions you will have one [extended] and the logical partitions will start from 5 cause the first 4 are reserved.
- Logical will always start from number 5. 
---
### Naming Conventions of disks

Here I suppose in each disk you have 3 partitions and the third is the extender and all logic partitons start from number 5

- PATA hard disks 
	- If you have 4 
	- hda -> partitions hda1 - hda2 - hda3  and logic hda5
	- hdb -> partitions hdb1 - hdb2 - hdb3  and logic hdb5
	- hdc -> partitions hdc1 - hdc2 - hdc3  and logic hdc5
	- hdd -> partitions hdd1 - hdd2 - hdd3  and logic hdd5
- SSD - SATA - SAS -  SCSI - Fash 
	- sda -> partitions sda1 - sda2 - sda3  and logic sda5
	- sdb -> partitions sdb1 - sdb2 - sdb3  and logic sdb5
	- sdc -> partitions sdc1 - sdc2 - sdc3  and logic sdc5
	- sdd -> partitions sdd1 - sdd2 - sdd3  and logic sdd5
- nvme0n1
	- A modern SSD (PCIe/NVMe).
- loop1
	- Virtual disk 
	- File being treated as a disk (often for Snaps or ISOs).

---
### lsblk 
To list all the disk storage in linux 
**`lsblk`**
