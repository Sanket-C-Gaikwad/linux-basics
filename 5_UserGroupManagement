## Linux User

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

## Properties of User account:
When you create a local user account, the user’s login information and all other details are stored in the /etc/passwd file.

```
cat /etc/passwd | grep -i sample

> sample:x:1003:1004:Sample User,123,123456789,805463638,Sample user:/home/sample:/bin/bash
> username:password:UID:GID:name:home directory:shell
```

## User creation, deletion, modifying commands.

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
