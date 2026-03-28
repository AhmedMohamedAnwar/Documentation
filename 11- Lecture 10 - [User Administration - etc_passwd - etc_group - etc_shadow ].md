### Lecture Link
- https://youtu.be/1i6jsUiMsUA?si=O9Nc1eApZDYT4A_H
---
### User Administration
#### Add user 
- If you didn't specify group to the new user linux will create primary group "with same name of the user ".

- If you added new user and the primary name of group that system will create by default already taken to other group the user will not be created.

```bash
useradd <username>
# Give primary group to user 
# The argument group should be created first
useradd -g <primary_group_name> <username> 
# To add default home directory to user 
useradd -m <username>
# give user default shell
useradd -s /bin/bash <username>
# Description for user 
useradd -c "Description" <username>
# assign uid to user
useradd -u 1500 <username>
```

- when you add user without -m it will write /home/username in passwd but it will not create directory in the file system.
- To fix run command by root:

```bash
# Create home dirctory of the user
mkhomedir_helper <username>
```
---
#### Add group
```bash
groupadd <groupname>
```
---
#### Modify user 
```bash
# To modify secondary group
# It will delete all old secondary groups and add new one in argument 
usermod -G <secondary_group_name>
# To add secondary group not delete existing 
usermod -a -G <secondary_group_name>
# To change user primary group 
usermod -g <primary_group_name>
# modify the shell type of user 
usermod -s /bin/bash <username>

```
#### User deleteion 
```bash
# To delete user [username - primary_group] not his files 
# If the user primary group was primary group to other group the user will be deleted but the group will remain 
userdel <username>
# To delete files + user
userdel -r <username> 
```
---
### /etc/passwd 

[/etc/passwd](https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/)

![[etc_passwd - Lecture 10.jpg]]

---
### /etc/group

[/etc/group](https://www.cyberciti.biz/faq/understanding-etcgroup-file/)

![[etc_group - Lecture 10.jpg]]

---
### /etc/shadow

[/etc/shadow](https://www.cyberciti.biz/faq/understanding-etcshadow-file/)

![[etc_shadow - Lecture 10.jpg]]

- The second place if found [!] mean no password set for this user.
---

