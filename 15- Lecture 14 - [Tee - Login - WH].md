### Lecture Link
- https://youtu.be/jYw-SHoSrfs?si=5BGladuxgvfHHPAS
---
### Tee
- Tee is use with other commands to show result in terminal and store in file like >
- Tee is used with | 
```bash
# Tee without other options override by default
ls | tee file.txt
# To avoide tee override use -a 
ls | tee -a file.txt
```
---
### Login and WH commands
#### w 
- Give you [connected users - uptime - load average of cpu]
- TTY [If there is :0 mean the user connected by tty on physical first monitor 0 is firest monitor :1 = second monitor]
- PTS [User connected remotely like ssh pts = emulator that emulate physical tty]
#### who 
- connected users
#### whatis
- `whatis ls` Give fast intro about command
#### whereis 
- Give you binary path of command `whereis python3`
#### last
- Give you all the last logins and reboots happens on the system.
#### lastlog
- Give you all the users in the system and thier last log to system.