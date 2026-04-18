### Lecture Link 
- https://youtu.be/9i_TGiq4fqo?si=3zJesA6JM-Ogu13i
--- 
### Symbols of `ls -al` 

| **-** | **Regular file**                                                 |
| ----- | ---------------------------------------------------------------- |
| **d** | **Directory**                                                    |
| **l** | **symbolic link "shortcut"**                                     |
| **b** | **Block device that can be hard drive that store data as block** |
| **c** | **character device like [mouse - keyboard - tty terminal]**      |
- To see that  run this command `ls -al /dev `
---
### Permission
- u -- user owner
- g -- group 
- o -- other 
---
- Ali created file so ali is the owner = u
- Hassan is not the owner but he is member of the group of the file = g 
- Amr is not owner nor in the group so he is other
---
* Suppose you are user that own file and have in u r only and you are member of the group with permission rwx like that `-r--rwx---` can you execute this file which you are member of it's group and own the file?
* No you will have the permissions of the owner ship cause system see are [owner] if yes take u permissions if no are you [in the group] if yes take g if no take other permissions.
---
- r   --   read         =[For files] **view**                   =[For directories] **`ls`** 
- w  --  write        =[For files] **edit + delete**  =[For directories] **add files or delete**
- x   --  execute   =[For files] **execute**            =[For directories] **`cd or ls -l`**

```bash 
# To add permissions 
chmod u+x <filename>
# Remove permission write and execute from user and group 
chmod ug-wx <filename>
# give permission to all "ugo"
chmod +x <filename>
# To give permissions to directory and all the content inside
chmod -R ug+x <filename>
```

---
### Ownership
```bash 
chown <username>:<groupname> <filename>
# Change user owner to ali
chown ali file.txt
# change group to workers
chown :workers file.txt
# change both 
chown ali:workers file.txt
```
---