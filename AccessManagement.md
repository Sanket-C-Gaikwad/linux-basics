##Manage File and Directory Permissions

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
| 2 | Number of links: The number of hard links to the file. For directories, this represents the number of entries within. |
| 3 | Owner: The username of the individual or entity that owns the file. |
| 4 | Group: The name of the group associated with the file. |
| 5 | Size: The file size in bytes. |
| 6, 7, 8 | Date and Time: The last modification date and time of the file, typically shown as `Month Day Time`. |
| 9 | Name: The name of the file or directory. For symbolic links, it also shows the link target. |
