### Lecture Link 
- https://youtu.be/G6rfNof0sVw?si=gwgGN1ha3kzinI5e
----
### How write goes in HDD

![[write in HDD Lecture 16.png]]

Writting in HDD happen by magnatic field in the first time ok when you want to write it for the second time you increase the magnatic field again.
So your disk come with 100 000 write only after that your disk can't read peak of the magnatic field.

---
### Copy from Inode prespective
##### Copy in same partition 
- First reserve Inode number.
- Write new blocks in the same partition. 
- Point new blocks to the new directory.
##### Copy in same different partition 
- First reserve Inode number in the new Inode table of the new partition.
- Write new blocks in the new partition.
- Point new blocks to the directory in the new partition. 
### Move from Inode prespective
##### Move in same partition  
- Keep the data blocks
- when same data blocks = same Inode number [cause we said each Inode number = data block].
- change the Directory pointer to the new directory you moved your file to.
##### Move in same different partition 
- First reserve Inode number in the new partition.
- Write new blocks in the new partition. 
- Point new blocks to the new directory.
- Update the old Inode number as free to use.
- What about blocks in the old partition ?  It will be the same will not deleted.
----
### Remove from Inode prespective
- Set Inode number as free.
- In disk there is no delete to data blocks you only overwrite data so if you delete data in disk and want to retrieve data again you should write again to same partition.
- https://youtu.be/G6rfNof0sVw?si=qEf2WMXaXZIh7vJy Video 24:30

![[retrieve data in disk Lecture 16.png]]

---
### NO 2 files can't have same Inode number in same partition but can 2 files in different partitions have same Inode.
---
### Soft Links
It's File that point to reference file not to Inode number.
Soft link file has Inode number.
Soft link can be in other partition in the disk.

| Original File | Inode |
| ------------- | ----- |
| File_1        | 500   |

| Soft Link File      | Inode  |
| ------------------- | ------ |
| Soft link to File_1 | 600    |
| Reference           | File_1 |
- If File_1 deleted your Soft link to File_1 can't work cause Inode 500 become free.
- In command with soft link you should use full path.

```shell
#Soft link original_file Soft_link.txt
ln -s Path_to_original_file Path_to_soft_link.txt
ln -s /root/file.txt /home/anwar/soft.txt
```
---
### Hard Links
It's File that point to same Inode number of the original file {another reference to the file}.
**Hard link can't be in other partition in the disk.** 

| Original File | Inode |
| ------------- | ----- |
| File_1        | 500   |

| Hard Link File      | Inode     |
| ------------------- | --------- |
| Hard link to File_1 | 500       |
| Reference           | Inode 500 |
- If File_1 deleted your Hard link to File_1 still work.
- These mean one of the reference deleted other can work.

```shell
#Hard link original_file Hard_link.txt
ln original_file Hard_link.txt
```
---
### Soft links can be used with Directories but Hard link can't be used with directories 
----
### Both Hard and Soft files when edited the original file will be edited too
---
