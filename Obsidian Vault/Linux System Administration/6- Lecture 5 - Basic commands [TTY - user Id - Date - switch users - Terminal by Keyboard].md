### Lecture Link
- https://youtu.be/J8hx35HfVfk?si=lYUy6fHpSwqMnVjq
---
### Open Terminal by Keyboard 
- alt + ctrl + t 
---
### TTY
- abbreviation for [tele type terminal].
- It's used when you have physical access to server.
- access it by alt + ctrl + [f2 or f3 ....] to return to GUI alt + ctrl + f1 -- each f for tty session.

```bash
 # Used to know which tty session you are on.
 tty 
```
---
### Users ID 
- **Root:** Take ID zero 
- **normal users:** Above 1000 

```bash
# To know the ID of your current user
id 
# To know the ID of any user
id <user>
```
---
### Date and Calender
```bash
# Date today 
date 
# Calender 
cal <month> <year> # Or use cal to get current month in current year

```
---
### Switch users

```bash
# login root user 
su 
# login normal user 
su - <username>
# exit 
exit 
```
---
