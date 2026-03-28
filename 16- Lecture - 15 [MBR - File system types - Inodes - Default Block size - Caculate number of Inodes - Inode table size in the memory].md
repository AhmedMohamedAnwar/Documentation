### Lecture Link
- https://youtu.be/onfq_eqZAF0?si=ruTI1fRCdjvjGIU8
----
### MBR 

![[MBR - Lecture 15.png]]

- MBR has 3 main rules 1- Contain **partition table**.
- Each storage you by for first time called row storage.
- **When you use it storage become partitions each partition is file system.**
- There is many file systems types that can each parttions use that mean it's not one type for all partitions.
---
#### File system types
- **In Linux** 
- https://www.geeksforgeeks.org/linux-unix/linux-file-system/

![[Linux File system - Lecture 15.jpg]]

- **In OS in General** 
- https://www.geeksforgeeks.org/operating-systems/file-systems-in-operating-system/

![[OS_File_Systems - Lecture 15.png]]

Each file system has **features** that support , **max volume** and **max file volume** inside.
- Example FAT32 -- max file size 4GB and doesn't support compression.

---

### Inodes

![[Inode - Lecture 15.png]]

- Your storage is blocks and numbered for example your storage is 10000 block.
- **Partition table** 
	- Partition 1 → blocks 1 to 750
	- Partition 2 → blocks 751 to 2000.
- **Inode table** contain data about files mean [block 750 has file 1 and all it's metadata like permissions and owner etc ...].
- The **partition table** exists **per storage device** (one per disk).
- The **inode table** exists **per partition** — every partition has its own inode table, independent from other partitions.
- If the inode table is **corrupted**, only its own partition will be affected — other partitions remain safe.
#### Each file should be represented by only **one** Inode number
---
### Different between file and directory
- **File** 

| **Inode number**      | File number that got from Inode table |
| --------------------- | ------------------------------------- |
| **Permission**        |                                       |
| **Owner**             |                                       |
| **Access time**       |                                       |
| **Creation time**     |                                       |
| **Modification time** |                                       |
| **Link count**        | **Number of [hard or soft] links**    |

---
- **Directory** 
- It's special file that contain pointer that point to files under it.
- Suppose you have Directory contain file1 and file 2.

| Inode number of Directory      | Directory number that got from Inode table |
| ------------------------------ | ------------------------------------------ |
| Permission                     |                                            |
| Owner                          |                                            |
| Access time                    |                                            |
| Creation time                  |                                            |
| Modification time              |                                            |
| Link count                     | Number of [hard or soft] links             |
| **Pointer to Inode of file 1** | Take inode of file1 to point to it         |
| **Pointer to Inode of file 2** | Take Inode of file 2 to point to it        |

---
### Default Block size 
- Each file system like [ext 2 - ext 3 - ext 4] have default size per block.
- When formating your disk you can change the default of the block size.

| **ext2** | **4 KB**  |
| -------- | --------- |
| **ext3** | **4 KB**  |
| **ext4** | **16 KB** |

- To know your file system type and size of block.
```bash
stat -f /
# Use it for other pathes
stat -f <path> 
```
---
### Caculate number of Inodes 

- **Inode Count = (Partition Size) \ (block size)** 

**Example 1 :**
- Your disk partition is 100 GB and you file system is ext4 and block size is default?
- **Inode Count = (100 GB = 107,374,182,400) \ (16 KB = 16384) = 6,553,600 inodes**

**Example 2 :**
- Your disk partition is 100 GB and you file system is ext4 and block size is customized to 1 GB?
- **Inode Count = (100 GB ) \ (1 GB ) = 100 inodes**
---
### Inode table size in the memory
- To calculate Inode table size 
- Each Inode number have memory size 128 bytes in [ext 2 - ext 3] and 256 bytes in [ext 4]
In the last example calculate space of Inode tables ?
- **Example 1 :** 6,553,600  *  256 bytes = 1.67 GB from 100 GB not used reserved for Inode table.
- **Example 2 :** 100  *  256 bytes = 25 KB from 100 GB not used reserved for Inode table.
---
### Bigger Block Size = Fewer Inodes = Fewer Files
---
### File size more than Inode size
We said each file represented by 1 Inode so If block size = 16K and I have file 32K so file will represented by first Inode number only but actually file reserve 2 Inodes but the first will only represent the file

---

# Continue from 1:30:50