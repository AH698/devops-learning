## Bandit Level 0 -> Level 1

**Challenge:**
Find the password stored in the `readme` file in the home directory.

**Solution:**
```bash
ls
cat readme
```

**Explanation:**
`ls` lists the files in the current directory.

`cat readme` displays the contents of the `readme` file.

**Password:**
[REDACTED]

**What I learned:**
I learned how to list files and read the contents of a text file.

---

## Bandit Level 1 -> Level 2

**Challenge:**
Read the password stored inside a file named `-`.

**Solution:**
```bash
ls
cat ./-
```

**Explanation:**
`ls` lists the files in the current directory.

A file named `-` could be mistaken for a command option.

`./-` tells Linux to use the file named `-` in the current directory.

**Password:**
[REDACTED]

**What I learned:**
I learned how to access files with unusual names and that `./` means the current directory.

---

## Bandit Level 2 -> Level 3

**Challenge:**
Read the password stored in a file with spaces in its filename.

**Solution:**
```bash
ls
cat "./--spaces in this filename--"
```

**Explanation:**
The filename contains spaces.

Putting the path inside quotes makes Bash treat the whole filename as one argument.

**Password:**
[REDACTED]

**What I learned:**
I learned how to work with filenames that contain spaces.

---

## Bandit Level 3 -> Level 4

**Challenge:**
Find the password stored in a hidden file inside the `inhere` directory.

**Solution:**
```bash
cd inhere
ls -a
cat ./.Hiding-From-You
```

**Explanation:**
`cd inhere` moves into the directory.

`ls -a` displays all files, including hidden files.

Files beginning with `.` are hidden in Linux.

**Password:**
[REDACTED]

**What I learned:**
I learned how hidden files work and how to display them using `ls -a`.

---

## Bandit Level 4 -> Level 5

**Challenge:**
Find the human-readable file inside the `inhere` directory.

**Solution:**
```bash
cd inhere
ls
file ./*
cat ./-file07
```

**Explanation:**
`ls` lists all the files.

`file ./*` checks the type of every file in the current directory.

`./*` means everything in the current directory.

The `file` command showed which file contained ASCII text.

**Password:**
[REDACTED]

**What I learned:**
I learned how to identify file types using `file`.

---

## Bandit Level 5 -> Level 6

**Challenge:**
Find a file that is:
- human-readable
- 1033 bytes
- not executable

**Solution:**
```bash
cd inhere
find . -type f -size 1033c ! -executable
cat ./maybehere07/.file2
```

**Explanation:**
`find .` searches from the current directory.

`-type f` searches for regular files.

`-size 1033c` means exactly 1033 bytes.

`! -executable` excludes executable files.

**Password:**
[REDACTED]

**What I learned:**
I learned how to combine different `find` filters to locate files based on their properties.

---

## Bandit Level 6 -> Level 7

**Challenge:**
Find a file somewhere on the server that:
- is owned by bandit7
- belongs to group bandit6
- is 33 bytes

**Solution:**
```bash
find / -type f -size 33c -user bandit7 -group bandit6
cat /var/lib/dpkg/info/bandit7.password
```

**Explanation:**
`find /` searches from the root of the filesystem.

`-user` filters by file owner.

`-group` filters by group.

`-size 33c` searches for exactly 33 bytes.

**Password:**
[REDACTED]

**What I learned:**
I learned how to search the entire filesystem using ownership, group and size conditions.

---

## Bandit Level 7 -> Level 8

**Challenge:**
Find the password next to the word `millionth` inside `data.txt`.

**Solution:**
```bash
grep "millionth" data.txt
```

**Explanation:**
`grep` searches text for matching words or patterns.

It returned the line containing `millionth` and the password.

**Password:**
[REDACTED]

**What I learned:**
I learned how to search inside files quickly using `grep`.

---

## Bandit Level 8 -> Level 9

**Challenge:**
Find the only line in `data.txt` that appears once.

**Solution:**
```bash
sort data.txt | uniq -u
```

**Explanation:**
`sort` places identical lines next to each other.

`|` sends the output into another command.

`uniq -u` displays lines that appear only once.

**Password:**
[REDACTED]

**What I learned:**
I learned how to combine commands using pipes and find unique data.

---

## Bandit Level 9 -> Level 10

**Challenge:**
Find the human-readable password inside `data.txt`.

**Solution:**
```bash
strings data.txt | grep "="
```

**Explanation:**
`strings` extracts readable text from binary data.

The output is piped into `grep` to filter the useful lines.

**Password:**
[REDACTED]

**What I learned:**
I learned how to extract readable text from binary files.

---

## Bandit Level 10 -> Level 11

**Challenge:**
Decode the Base64 encoded password stored in `data.txt`.

**Solution:**
```bash
man base64
base64 -d data.txt
```

**Explanation:**
`man base64` displays the manual page for the command.

`base64 -d` decodes Base64 encoded data.

**Password:**
[REDACTED]

**What I learned:**
I learned how to use manual pages and decode Base64 data.

---

## Bandit Level 11 -> Level 12

**Challenge:**
Decode text where the letters have been rotated by 13 positions.

**Solution:**
```bash
cat data.txt
strings data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```

**Explanation:**
The data uses ROT13.

`tr` translates characters from one set into another.

The second alphabet represents the 13-position rotation.

**Password:**
[REDACTED]

**What I learned:**
I learned how `tr` works and how ROT13 encoding can be reversed.

---

## Bandit Level 12 -> Level 13

**Challenge:**
Recover a password from data that has been repeatedly compressed in different formats.

**Solution:**
```bash
mkdir -p /tmp/bandit-work
cp data.txt /tmp/bandit-work
cd /tmp/bandit-work

xxd -r data.txt data
file data
```

Then repeatedly used:

```bash
file
gzip -d
bzip2 -d
tar -xf
```

**Explanation:**
`xxd -r` reverses a hexadecimal dump back into binary data.

`file` identifies the current file format.

I repeatedly checked the file type and then used the correct extraction or decompression command.

**Password:**
[REDACTED]

**What I learned:**
I learned how to work through several layers of compression using `file`, gzip, bzip2 and tar.

---

## Bandit Level 13 -> Level 14

**Challenge:**
Use the provided SSH private key to log into the next Bandit account.

**Solution:**
```bash
scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .
chmod 600 sshkey.private
ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org
```

**Explanation:**
`scp` securely copies files between machines.

`chmod 600` allows only the owner to read and write the private key.

`ssh -i` specifies which private key to use when connecting.

**Password:**
N/A - SSH key used

**What I learned:**
I learned how SSH key authentication works and why private key permissions must be restricted.

---

## Bandit Level 14 -> Level 15

**Challenge:**
Send the current password to a service running on port 30000 on localhost.

**Solution:**
```bash
cat /etc/bandit_pass/bandit14
nc localhost 30000
```

**Explanation:**
`cat` displays the current Bandit password.

`nc` uses Netcat to connect to a network service.

`localhost` means the current machine and `30000` is the port number.

I entered the current password and received the password for Bandit 15.

**Password:**
[REDACTED]

**What I learned:**
I learned how to use Netcat to connect to a service on a specific network port.
