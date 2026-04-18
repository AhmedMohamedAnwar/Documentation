### Lecture Link 
- https://youtu.be/Fi8gew5YIFM?si=C4QkceGMIghHKKnu
---
### Terminal shotcuts 
#### ctrl + a 
- To move the cursor to the start of command 
#### ctrl + e 
- To move the cursor to the end of command 
#### ctrl + k
- To delete from cursor to end of command "delete to rigth"
#### ctrl + u
- To delete from cursor to the start of command "delete to left"
#### ctrl + d 
- Logout == exit 
#### ctrl + l 
- clear the screen by shift page == clear 
#### ctrl + z 
- Pause the command execution 

```bash 
# To continue run:
bg
```
#### ctrl + c 
- Interrupt the command execution 
#### ctrl + s
-  lock screen and the output of your commands you made the shortcut on.
#### ctrl + q
- show command and it's output you made ctrl + s on.
#### ctrl + alt + t
- Open new terminal.
#### Excute two commands togther
```bash
ls ; date 
```

---
### Reboot machine 
```bash 
# To reboot machine use one of this commands 
reboot
systemctl reboot 
shutdown -r now 
init 6
```
---
### shutdown machine 
```bash 
# To shutdown machine use one of this commands 
poweroff
systemctl poweroff 
shutdown -h now 
init 0
```
---
### add user + change password 
 -   To change the password of any user you should be root 
 -  `passwd` only will change the password to current user and if you are not root and put bad password it will not be accepted 
 ```bash
 # To add user 
 useradd ali 
 # To change passsword of any user 
 passwd ali 
 ```
 ---