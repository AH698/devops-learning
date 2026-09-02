# Linux Notes

A summary of the Linux fundamentals I have covered while building my DevOps foundations.

## LINUX BASICS

Linux is an operating system widely used for servers, cloud infrastructure and DevOps environments. A lot of Linux administration can be carried out directly through the terminal.

Some basic commands I have used include:

`pwd` - Shows the current working directory.

`ls` - Lists files and directories.

`cd` - Changes directory.

`whoami` - Shows the current user.

`history` - Shows previously executed commands.

`man` - Opens the manual for a command.


## FILES AND DIRECTORIES

Linux provides commands for creating, copying, moving, renaming and deleting files and directories.

`touch` - Creates a file.

`mkdir` - Creates a directory.

`cp` - Copies files or directories.

`mv` - Moves or renames files.

`rm` - Removes files or directories.

I also learned how Linux paths work. `./` represents the current directory, `..` represents the parent directory and `~` represents the current user's home directory.


## FINDING AND READING FILES

Linux provides several tools for finding files and viewing their contents.

`find` - Searches for files and directories based on conditions such as name, type or size.

`cat` - Displays the contents of a file.

`less` - Allows file contents to be viewed one screen at a time.

`head` - Displays the beginning of a file.

`tail` - Displays the end of a file.

`tail -f` - Follows a file as new content is added, which is particularly useful when monitoring logs.


## WORKING WITH TEXT

Linux has powerful tools for searching and processing text.

`grep` - Searches for matching text.

`sort` - Sorts lines of text.

`uniq` - Filters repeated adjacent lines.

`cut` - Extracts selected parts of each line.

`tr` - Translates or replaces characters.

`awk` - Processes structured text and fields.

`sed` - Performs text transformations.

`wc` - Counts lines, words or characters.

I also learned how pipes (`|`) pass the output of one command into another. This allows multiple Linux tools to be combined to complete more useful tasks.


## USERS, GROUPS AND PERMISSIONS

Linux permissions control who can access files and what actions they can perform.

The three main permissions are:

- Read (`r`)
- Write (`w`)
- Execute (`x`)

Permissions are applied to the user who owns the file, the group associated with it and other users.

`chmod` - Changes file permissions.

`chown` - Changes file ownership.

Understanding permissions is important for controlling access and keeping Linux systems secure.


## PROCESSES AND JOBS

A process is a running instance of a program.

`ps` - Displays running processes.

`ps aux` - Shows a more detailed list of processes.

`top` - Provides a live view of processes and system resource usage.

`kill` - Sends a signal to a process using its PID.

I also covered:

`jobs` - Shows jobs associated with the current shell.

`bg` - Continues a stopped job in the background.

`fg` - Brings a job into the foreground.

`nohup` - Allows a command to continue running after the terminal session closes.


## DISK USAGE

`df -h` - Shows filesystem capacity, used space and available space in a human-readable format.

`du -sh <directory>` - Shows how much disk space a particular directory is using.

The main difference is that `df` looks at filesystem capacity, while `du` looks at the space being consumed by files and directories.


## ARCHIVES AND COMPRESSION

I have worked with several common Linux tools for archives and compression.

`tar` - Packages files and directories into an archive.

`gzip` - Compresses files using gzip compression.

`bzip2` - Compresses files using bzip2 compression.

An archive packages files together, while compression reduces the amount of storage the data requires.


## SSH

SSH provides secure remote command-line access to another machine.

Example:

`ssh user@host`

I have used SSH practically to connect from a local Linux environment to a remote Ubuntu server. This helped me understand how Linux servers can be managed remotely without needing a graphical interface.


## NETWORKING COMMANDS

I have used several Linux commands for inspecting network configuration and troubleshooting connectivity.

`ip addr` - Displays network interfaces and their IP addresses.

`ping` - Tests connectivity to another host.

`ss -ltn` - Displays TCP ports that are currently listening for connections.

These commands are useful for understanding the state of a machine before investigating wider network problems.


## SERVICES AND LOGS

Linux services can be managed using `systemctl`.

`systemctl start <service>` - Starts a service.

`systemctl status <service>` - Checks the current status of a service.

`systemctl enable <service>` - Configures a service to start automatically at boot.

I have used these commands when managing NGINX on an Ubuntu server.

For troubleshooting, I have also used:

`journalctl -u <service>` - Displays logs for a specific systemd service.

`journalctl -u <service> -f` - Follows new log entries as they are created.

This makes it possible to check not only whether a service has failed, but also investigate why it failed.


## PACKAGE MANAGEMENT

Ubuntu uses APT for package management.

`sudo apt update` - Refreshes the local package index.

`sudo apt install <package>` - Installs a package.

Understanding the difference between updating the package index and actually installing or upgrading software helped me troubleshoot package installation problems.


## KEY TAKEAWAYS

My Linux learning so far has given me a foundation in:

- Navigating and managing the Linux filesystem
- Finding files and processing text
- Managing users, groups and permissions
- Monitoring processes and jobs
- Checking filesystem and disk usage
- Working with archives and compression
- Connecting to remote machines with SSH
- Using Linux networking tools
- Managing services and investigating logs
- Managing software packages

The biggest thing I have taken from Linux is that understanding why a command is being used is more valuable than simply memorising it. Knowing what information each command provides makes it much easier to choose the right tool when troubleshooting a problem.
