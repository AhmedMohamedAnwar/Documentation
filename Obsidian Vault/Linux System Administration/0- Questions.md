### **Q1: Are files in `/tmp` deleted on session exit or reboot?**

- **Exit SSH/Logout:** **No.** The filesystem stays active; only your session ends.
- **System Reboot:** **Yes.** `/tmp` is usually stored in **RAM** (tmpfs), which clears on restart.
- **Long-term:** **Yes.** Systems run "cleanup" scripts that delete files older than 10–30 days.
---
### Q2: Can member of group of files change permissions of file? 

- No only the owner and root can change permissions of file.
---
### Q3: 

---
