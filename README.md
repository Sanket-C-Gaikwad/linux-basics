| Command | Purpose | Detailed Examples |
|---------|---------|-------------------|
| touch | Creates an empty file or updates its timestamp. | `touch newfile.txt` - Creates a new file.<br>`touch -a file.txt` - Updates the access time only. |
| chmod | Changes the file's mode (permissions). | `chmod 755 script.sh` - Sets read, write, execute permissions for the owner, read and execute for others.<br>`chmod +x script.sh` - Adds execute permission. |
| chown | Changes the file or directory's ownership. | `chown user:group file.txt` - Changes ownership to user and group.<br>`chown user file.txt` - Changes file owner to user. |
| df | Displays the disk space usage. | `df -h` - Shows disk usage in a human-readable format.<br>`df -i` - Displays inodes information. |
| du | Estimates the file space usage. | `du -sh /home/user` - Shows space used by the `/home/user` directory.<br>`du -a /home/user` - Shows space for all files. |
| tail | Displays the last part of a file. | `tail -n 10 file.txt` - Shows the last 10 lines.<br>`tail -f log.txt` - Continuously monitors log updates. |
| head | Displays the first part of a file. | `head -n 5 file.txt` - Shows the first 5 lines.<br>`head -n -2 file.txt` - Excludes the last 2 lines. |
| diff | Compares files line by line. | `diff file1.txt file2.txt` - Shows differences.<br>`diff -u file1.txt file2.txt` - Shows unified diff. |
| tar | Manages tar archives. | `tar -czvf archive.tar.gz /path/to/dir` - Creates a compressed archive.<br>`tar -xvzf archive.tar.gz` - Extracts the archive. |
| wget | Downloads files from the internet. | `wget http://example.com/file.txt` - Downloads a file.<br>`wget -c http://example.com/file.txt` - Continues an interrupted download. |
| curl | Transfers data from or to a server. | `curl http://example.com` - Fetches the webpage.<br>`curl -o page.html http://example.com` - Saves output to `page.html`. |
| ps | Reports a snapshot of current processes. | `ps aux` - Shows all running processes.<br>`ps -ef` - Displays processes in full format. |
| kill | Sends a signal to a process. | `kill -9 1234` - Forcefully stops the process.<br>`kill -SIGTERM 1234` - Sends a termination request. |
| nano/vi | Opens a text editor in the terminal. | `nano file.txt` - Opens `file.txt` in nano.<br>`vi file.txt` - Opens `file.txt` in vi. |
| ln | Creates links between files. | `ln -s original.txt link.txt` - Creates a symbolic link.<br>`ln original.txt hardlink.txt` - Creates a hard link. |
| top | Displays active processes in real-time. | `top` - Displays running processes.<br>`top -u user` - Shows processes for a specific user. |
| netstat | Displays network connections and statistics. | `netstat -tuln` - Lists listening ports.<br>`netstat -r` - Shows the routing table. |
| crontab | Manages cron jobs for scheduled tasks. | `crontab -e` - Edits the cron jobs.<br>`crontab -l` - Lists cron jobs. |
