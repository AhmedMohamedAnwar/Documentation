### Lecture Link 
- https://youtu.be/KGnmy_cYwUs?si=kBn3qA0wjUAeTomM
---
### Service "System" User 
- From ID = 1-999 are dummy users used to run only the services on machine but can't do anything to any files except the service files only.
- Service users doesn't have any privillages and can't create login shell to your machine.
- These users is made to avoid hack of any service if any service hacked the users will not get access to the machine cause the dummy user will have the access to service only.
---
### FHS [File System Hierarchy]
#### Role: Every thing in Linux is a file your devices "mouse - keyboard - disk partitions" all are files under the file system. 

- **Visit this site to see example on each file system.**
- https://www.geeksforgeeks.org/linux-unix/linux-file-hierarchy-structure/

![[Linux_File_Hierarchy - Lecture 6 FHS.jpg]]

**sbin:** superuser binary contain all the administrative commands that only used by root user.
**bin:** contain all the command that any user can use like [ls - cat - mkdir - etc...].
**proc:** 
- All the info that kernal collect about users ids and cpu stored in that directory for example all info kernal know stored in /proc/cpuinfo.
- proc is read only and kernal only can write on.
- proc is virtual file system.
**tmp:** for temporary files that app use "and you can write on this file system"  the temporary files will be removed by two ways:
- system reboot.
- auto clean which you can custom the time of cleaning.
**opt:** Is used for installing some apps inorder to be easy to uninstall the app like orcale.
**media:** It's the file system that will contain the mounted device like usb flash memory or CD room.

---



