# User Management 
---
User management allows us to create multiples user on linux using user management tools. This helps our file stay private as users can not have access to other users file. A user is basically who 
we are in a linux terminal while a group is basically identify which team we belong to and what permissions we have. A root user have privilege to not only control users but also have access to system file 
while a standard user can mess around with personal files. Using Sudo command can actually give a standard user root privileges. '

--- 
# Tools 
* Useradd: adds a user
* Userdel: deletes a user
* Usermod: Modifies existing user can change group ownership
* passwd: creates password for a user

  <img width="326" height="131" alt="Screenshot 2026-09-08 215018" src="https://github.com/user-attachments/assets/01a28bdf-1913-48ed-948d-8f62ca605b5d" />

---

# File management
---
The purpose of file management is to allow who can read, write, and execute a file. It is very important to give permissions to specific class. There are three types of classes involved in this. 
- User
- Group 
- Others
we mainly give read, write, execute permissions to user. 

# Understanding 'r,w,x'

'r,w,x' is basically read, write, and execute. These permissions are given to our classes by using commands.

---
# File management tools
We can change permission by using chmod (change mode) it changes file permission but before we need to understand how permissions looks like by using command ls -l we see something like this
* -drwx-xr-x
d represents directory, - for a regular file, l for a symbolic link. 'u' selects for user, 'g' for groups 'o' for others, and 'a' for all three.

<img width="547" height="274" alt="Screenshot 2026-09-08 215136" src="https://github.com/user-attachments/assets/7a312876-b554-40b5-9a2d-49da1230c9a8" />

---
# using the commands
---
# File management. 
chmod u+x (gives user permission to execute a file) notes.txt 
chmod g-r (denies group to read a file) notes.txt

---
<img width="317" height="55" alt="Screenshot 2026-09-08 215454" src="https://github.com/user-attachments/assets/ac3ce8e8-13a6-4c5f-9a96-5a1cf3abec1c" />

---
# Octal mode 
use digits to set permissions. 
* 4 for read 
* 2 for write 
* 1 for execute 
* 0 for no permissions
  
---
<img width="238" height="34" alt="Screenshot 2026-09-08 215605" src="https://github.com/user-attachments/assets/b4ffd16b-3763-4c8e-a4d7-cda8cde63f6d" />


owner = 7 (4+3+1)
group = 5 (4+1)
others = 5 (4+1)

---
# Ownership permissions 
we use chown (change owner) to change owner of a file. Example --sudo chown josh file.txt-- the owner of this file is now josh
to change both user and group we can simply do this 
-sudo chown taas:developers file.txt

---
# Umask
takes away the permission when a file is created for example file.txt has rwx for every class running umask will take away some of the permission depends on how we set it
for example umask 022 

---
# SetUID 
it is a special file permission that allows a user to run an executable file with the privileges of a file owner 
chmod u+s file.txt

<img width="588" height="311" alt="Screenshot 2026-09-08 215913" src="https://github.com/user-attachments/assets/9d4fa722-7639-4b2d-b4f5-67cdac267a9c" />

