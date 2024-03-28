## 1 Linux User

# 1 System User:
A system user account aka privileged account is created by the operating system during its installation and that is used for operating system defined purposes. They have user id's predefined (100-999).

```
cat /etc/login.defs  | grep -i SYS_UID_MIN
cat /etc/login.defs  | grep -i SYS_UID_MAX
cat /etc/login.defs  | grep -i SYS_GID_MIN
cat /etc/login.defs  | grep -i SYS_GID_MAX

```

# 2 Regular User: 
The regular user accounts has ids begin from 1000 onwards.

```
cat /etc/login.defs  | grep -i UID_MIN | grep -v -E '^\#'
cat /etc/login.defs  | grep -i UID_MAX | grep -v -E '^\#'
cat /etc/login.defs  | grep -i GID_MIN | grep -v -E '^\#'
cat /etc/login.defs  | grep -i GID_MAX | grep -v -E '^\#'

``` 

## 2 Properties of User account:
When you create a local user account, the user’s login information and all other details are stored in the /etc/passwd file.

```
cat /etc/passwd | grep -i sample

> sample:x:1003:1004:Sample User,123,123456789,805463638,Sample user:/home/sample:/bin/bash
> username:password:UID:GID:name:home directory:shell
```

## 3 User creation, deletion, modifying commands.

```
adduser username

> adding passwrod
passwd username    

> -r remove all home dir, -f force remove
userdel -r username  

> comment
usermod -c "This is Sample user" sample 

> directory
usermod -d /var/www/ sample

> expiry date
usermod -e 2021-12-04 sample

> check status of expiry and change
chage -l sample

> Lock
usermod -L sample

> Unlock
usermod -U sample
```

## 4 Group Management
There are two types of groups in Linux. The primary group and secondary group. On Linux when you create a user the primary group that the user belongs to also gets created with the same name as the user.

A user must be a member of a primary group and there can be only one primary group for each member. Secondary groups are always optional. If you have a requirement create it and add the users to it. A user can be mart of one or more secondary groups.

Here, sanket is part of its own primary group sanket. with GID 1000
cat /etc/passwd | grep -i sanket
sanket:x:1000:1000:,,,:/home/sanket:/bin/bash

# Group management commands:

```
groupadd grpname
cat /etc/group | tail -l

usermod -G group2 username
cat /etc/group | grep grpname

> Check grp info using id and groups
id username
groups username

> Change group name
groupmod -n newname oldname

> Change GID
groupmod -g 1005 grpname

> Remove a User from a Linux group
gpasswd -d username groupname

> Group delete
groupdel groupname
```

## 5 Advance User:
It has a primary group and multiple secondary group with shell instruction

```
groupadd primary
groupadd secondary1
groupadd secondary2

useradd -c "Advance user" -g primary -G secondary1,secondary2 -s /bin/sh user2

```

## 6 How users and groups database is maintained
On Linux Operating system there are primarily four files placed under /etc directory which manages records about users and groups.

/etc/passwd -> The file containing basic information about users.

/etc/shadow -> The file containing encrypted passwords.

/etc/group -> The file containing basic information about groups and which users belong to them.

/etc/gshadow -> The containing encrypted group passwords.


## 7 What is purpose of having group password

It's a very common question one can ask you in interviews. If we protect a group by setting password to it the non-members can join the group by typing the password for that group using the newgrp command.

If the value of this field is set to ! then no user is allowed to access the group using the newgrp command only the user with admin access can make changes. A value of !! indicates that a password has never been set before. If the value is null, only group members will be allowed to log into the group. This file is not of much importance though.

```
> change passwoord
gpasswd joingroup

> Chnage user
su - username

pwd

id

> now try to join new group
newgrp joingroup

```
