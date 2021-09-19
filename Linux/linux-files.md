## Linux Administration Week

Hector M Molina Sandoz
Week 4 - Submission File: Linux Systems Administration


Step 1: Ensure/Double Check Permissions on Sensitive Files
Permissions on /etc/shadow should allow only root read and write access.
Command to inspect permissions:


```
sysadmin@UbuntuDesktop:/$ ls -l /etc/shadow
-rw------- 1 root shadow 2863 Jul  7 22:30 /etc/shadow
```

Command to set permissions (if needed):
```
sysadmin@UbuntuDesktop:/$ sudo chmod 600 /etc/shadow
```


Permissions on /etc/gshadow should allow only root read and write access.
Command to inspect permissions:
```
sysadmin@UbuntuDesktop:/$ ls -l /etc/gshadow
-rw------- 1 root shadow 1068 Jul  7 22:30 /etc/gshadow
```

Command to set permissions (if needed):
```
sysadmin@UbuntuDesktop:/$ sudo chmod 600 /etc/gshadow
```

Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:
```
sysadmin@UbuntuDesktop:/$ ls -l /etc/group
-rw-r--r-- 1 root root 1292 Jul  7 22:30 /etc/group
```

Command to set permissions (if needed):
```
sysadmin@UbuntuDesktop:/$ sudo chmod 644 /etc/group
```


Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.
Command to inspect permissions:
```
sysadmin@UbuntuDesktop:/$ ls -l /etc/passwd
-rw-r--r-- 1 root root 3159 Jul  7 22:30 /etc/passwd
```

Command to set permissions (if needed):
```
sysadmin@UbuntuDesktop:/$ sudo chmod 644 /etc/passwd
```


Step 2: Create User Accounts
Add user accounts for sam, joe, amy, sara, and admin.
Command to add each user account (include all five users):
```
sysadmin@UbuntuDesktop:/$ sudo adduser sam
sysadmin@UbuntuDesktop:/$ sudo adduser joe
sysadmin@UbuntuDesktop:/$ sudo adduser amy
sysadmin@UbuntuDesktop:/$ sudo adduser sara
sysadmin@UbuntuDesktop:/$ sudo adduser admin
```

Ensure that only the admin has general sudo access.
Command to add admin to the sudo group:
```
sysadmin@UbuntuDesktop:/$ sudo usermod -aG sudo admin
```


Step 3: Create User Group and Collaborative Folder
Add an engineers group to the system.
Command to add group:
```
sysadmin@UbuntuDesktop:/$ sudo addgroup engineers
[sudo] password for sysadmin: 
Adding group `engineers' (GID 1019) ...
Done.
```

Add users sam, joe, amy, and sara to the managed group.
Command to add users to engineers group (include all four users):

```
sysadmin@UbuntuDesktop:/$ sudo usermod -aG engineers sam
sysadmin@UbuntuDesktop:/$ sudo usermod -aG engineers joe
sysadmin@UbuntuDesktop:/$ sudo usermod -aG engineers amy
sysadmin@UbuntuDesktop:/$ sudo usermod -aG engineers sara
```


Create a shared folder for this group at /home/engineers.
Command to create the shared folder:
```
sysadmin@UbuntuDesktop:/home$ sudo mkdir /home/engineers
```

Change ownership on the new engineers' shared folder to the engineers group.
Command to change ownership of engineer's shared folder to engineer group:
```
sudo chgrp engineers /home/engineers
```


Step 4: Lynis Auditing
Provide a report from the Lynis output on what can be done to harden the system.

 
Bonus
Command to install chkrootkit:
```
sysadmin@UbuntuDesktop:/$ sudo apt install chkrootkit
```
 

Command to see documentation and instructions:
```
sysadmin@UbuntuDesktop:/$ man chkrootkit
```
 
Command to run expert mode:
```
sysadmin@UbuntuDesktop:/$ chkrootkit -X
```

