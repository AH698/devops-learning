**Linux Notes**

These notes summarise the Linux fundamentals I have covered while
building my DevOps foundations.

**Linux Basics**

Linux is an operating system widely used for servers, cloud
infrastructure and DevOps environments. A lot of Linux administration is
carried out through the terminal, where commands can be used to manage
files, users, processes, services and the system itself.

Some basic commands I have used include:

pwd
ls
cd
whoami
history
man

pwd shows the current directory, ls lists its contents and cd is
used to move between directories. man is useful for checking a
command's documentation and available options.

**Files and Directories**

Linux provides commands for creating, moving, copying and removing files
and directories.

touch
mkdir
cp
mv
rm

I also learned how paths work, including the difference between absolute
and relative paths. ./ refers to the current directory, .. refers to
the parent directory and ~ represents the current user's home
directory.

**Finding and Reading Files**

Linux has several useful tools for locating files and viewing their
contents.

find
cat
less
head
tail

find can search based on conditions such as name, type and size.
head and tail display the beginning or end of a file, while
tail -f can follow a file as new content is added, which is useful for
monitoring logs.

**Working with Text**

Text-processing commands are useful for searching through files, logs
and command output.

grep
sort
uniq
cut
tr
awk
sed
wc

For example, grep searches for matching text, sort orders output,
uniq helps remove repeated lines and wc can count lines or words.

I also learned how pipes can pass the output of one command into
another:

command1 | command2

This allows small Linux tools to be combined to perform more useful
tasks.

**Users, Groups and Permissions**

Linux permissions control who can access files and what they are allowed
to do with them.

The main permissions are:

Read (r)

Write (w)

Execute (x)

They apply to the file owner, group and other users.

Useful commands include:

chmod
chown

chmod changes permissions and chown changes file ownership.
Understanding permissions is important for both system administration
and security.

**Processes and Jobs**

A process is a running instance of a program.

ps
ps aux
top
kill

ps provides information about running processes, top gives a live
view of processes and resource usage, and kill can send a signal to a
process using its PID.

I also covered background and foreground jobs using:

jobs
bg
fg
nohup

nohup is useful when a command needs to continue running after the
terminal session closes.

**Disk Usage**

Two important commands for checking storage are:

df -h
du -sh <directory>

df shows filesystem capacity and available space, while du shows how
much space files or directories are using.

**Archives and Compression**

I worked with common Linux archive and compression tools including:

tar
gzip
bzip2

tar is commonly used to package files together, while gzip and
bzip2 compress data.

**SSH**

SSH allows secure remote access to another machine from the command
line.

ssh user@host

I have used SSH practically to connect from a local Linux environment to
a remote Ubuntu server. This helped me understand how Linux servers can
be managed remotely without needing a graphical interface.

**Networking Commands**

I have also used Linux tools to inspect network configuration and
troubleshoot connectivity.

ip addr
ping
ss -ltn

ip addr displays network interfaces and IP addresses, ping can test
connectivity, and ss -ltn shows TCP ports that are currently listening
for connections.

**Services and Logs**

Linux services can be managed with systemctl.

sudo systemctl start <service>
sudo systemctl status <service>
sudo systemctl enable <service>

I used these commands when working with NGINX on an Ubuntu server.

For troubleshooting services, I also used journalctl:

sudo journalctl -u <service>

This allows logs for a particular service to be inspected when something
is not working as expected.

Package Management

On Ubuntu, APT is used to manage software packages.

sudo apt update
sudo apt install <package>

apt update refreshes the local package information, while
apt install installs a selected package.

**Key Takeaways**

My Linux learning so far has given me a foundation in navigating and
managing a Linux system, working with files and permissions, monitoring
processes and storage, accessing remote machines, managing services and
using command-line tools to troubleshoot problems.

The main thing I have taken from Linux is that understanding why a
command is being used is more valuable than simply memorising it.
Knowing what information a command gives me makes it much easier to
choose the right tool when solving a problem.
