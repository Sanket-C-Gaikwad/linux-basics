## 1. Manage File and Directory Permissions

- To view the file and directory permissions:
```
ls -la
```

- Output:
```
total 12
drwxr-xr-x 2 sanket sanket 4096 Oct 19 12:53 feature122
drwxr-xr-x 2 sanket sanket 4096 Oct 26 12:45 feature152
drwxr-xr-x 5 sanket sanket 4096 Oct 21 10:28 sanket.gaikwad1
```

| Column | Meaning |
|--------|---------|
| 1 | File type and permissions: A string of 10 characters where the first character represents the file type (`-` for a regular file, `d` for a directory, `l` for a symbolic link, etc.). The following nine characters are grouped in threes, representing the read (`r`), write (`w`), and execute (`x`) permissions for the owner, group, and others, respectively. |
| 2 | Number of links: The number of hard links to the file. For directories, this represents the number of entries within. ``` stat dir_name```, permanent links when we create dir or file is, . for current dir, and .. for parent dir, when we do ```ls -la``` we can see links highlighted in diff. colors|
| 3 | Owner: The username of the individual or entity that owns the file. |
| 4 | Group: The name of the group associated with the file. |
| 5 | Size: The file size in bytes. |
| 6, 7, 8 | Date and Time: The last modification date and time of the file, typically shown as `Month Day Time`. |
| 9 | Name: The name of the file or directory. For symbolic links, it also shows the link target. |


## 2. How do I Change Permissions?

```
chmod [OPTIONS] [ugoa…][-+=]perms…[,…] FILE/DIR...
```

| Component | Meaning |
|-----------|---------|
| `OPTIONS` | Optional flags to alter the behavior of `chmod`. For example, `-R` applies changes recursively. |
| `ugoa`    | User classes the changes will apply to: `u` (user/owner), `g` (group), `o` (others), `a` (all). Omitting this applies changes to all by default. |
| `-+=`     | Operators that define how permissions change: `+` adds, `-` removes, and `=` sets exactly. |
| `perms`   | Specifies the permissions: `r` (read), `w` (write), `x` (execute). Can combine multiple permissions. |
| `[,…]`    | Allows specifying multiple changes, separated by commas, each for different user classes. |
| `FILE/DIR`| The target file or directory to change permissions for. |


- Examples:

> To grant the user full permissions, the group read and execute permissions, and remove all permissions from others for `file.txt`:
```
chmod u+rwx,g+rx,o-rwx file.txt
```

> To set read-only permissions for everyone for file.txt:
```
chmod a=r file.txt
```

> Give the owner of the demo_file full permissions (read, write and execute)
```
chmod u=rwx demo_file
```

> Give the write permission for group members:
```
chmod g+w demo_file
```

> Recursively remove the write permission for group users:
```
chmod -R g-w demo_file
```

> Give execute permission to all:
```
chmod a+x demo_file
chmod a=rw demo_file
```

> Remove all permissions:
```chmod go= demo_file```

- Numeric Method
```
chmod [OPTIONS] NUMBER FILE/DIR...

```
| Component  | Meaning |
|------------|---------|
| `OPTIONS`  | Optional flags to alter the behavior of `chmod`. For example, `-R` applies changes recursively. |
| `NUMBER`   | A three-digit octal number where each digit represents permissions for the user, group, and others, respectively. |
| `FILE/DIR` | The target file or directory to change permissions for. |

| Number | Permission | Description |
|--------|------------|-------------|
| 7      | rwx        | Read, write, and execute |
| 6      | rw-        | Read and write |
| 5      | r-x        | Read and execute |
| 4      | r--        | Read only |
| 3      | -wx        | Write and execute |
| 2      | -w-        | Write only |
| 1      | --x        | Execute only |
| 0      | ---        | No permission |

- Examples:
The `chmod` command can be used with these numbers to set file permissions. For example:
- `chmod 755 FILE/DIR`: Sets the permissions to `rwx` for the owner, and `r-x` for both the group and others.
- `chmod 644 FILE/DIR`: Sets the permissions to `rw-` for the owner, and `r--` for both the group and others.



