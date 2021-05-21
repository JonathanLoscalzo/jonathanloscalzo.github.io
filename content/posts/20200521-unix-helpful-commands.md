+++ 
draft = false
date = 2021-05-21T12:09:46-03:00
title = "Some Bash/unix helpful commands"
description = ""
slug = ""
authors = []
tags = ["bash", "unix"]
categories = []
externalLink = ""
series = []
+++


# Bash/Unix Commands
- [AWESOME CHEATSHEETS, BASH](https://github.com/LeCoupa/awesome-cheatsheets/blob/master/languages/bash.sh)
- [Devhit - bash](https://devhints.io/bash)
- [Hostinger - Linux Commands](https://www.hostinger.com/tutorials/linux-commands)
- [Guru99 - Linux cheathsheet](https://www.guru99.com/linux-commands-cheat-sheet.html)

### ls

```
ls -a # hidden files
ls -la # large list, more information
ls -lah # size in kb
ls -R # list recursively
```

In .bashrc: 
```
alias ll = "ls -lahF"
```
### rsync
- [Rsync - wikipedia](https://es.wikipedia.org/wiki/Rsync)
- [Linux Techie - Rsync](https://www.linuxtechi.com/rsync-command-examples-linux/)
- [Hostinger - Rsync](https://www.hostinger.com.ar/tutoriales/rsync-linux)

```
rsync  file  dest/
rsync dir/* dest/
rsync -a dir/ dest/ # file mode
rsync -av dir/ dest/ # verbose
rsync -azv dir/ dest/ # compress during transfering
rsync -av --dry-run dir/ dest/ # execution without result, only to evaluate output.
rsync -a --delete dir/ dest/ # file mode, remove files in destiny that are not in source. 
rsync -aP dir/ dest/ # progress bar

rsync [optional modifiers] [USER@]HOST:SRC [DEST] # pull
rsync [optional modifiers] SRC [USER@]HOST:[DEST] # push
```

### touch
https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/
The touch command is a standard command used in UNIX/Linux operating system which is used to create, change and modify timestamps of a file.
alternative command: `cat`

```
touch file1
touch file1 file2
touch file{1..2}
touch -a file1 # change access time 
touch -m file1 # change modification
```

### du (disk usage)
Summarize disk usage of the set of FILEs, *recursively for directories*. 

[geeksforgeeks - du](https://www.geeksforgeeks.org/du-command-linux-examples/)


```
dh 
dh -h # human readable, list with measure (kbytes, mbytes...)
du -h . | sort -hr | head -n3 # list 3 most weighted files/directories on actual directory
du -h * | sort -hr | head -n3 # this doesn't show "." or actual directory...

du -hc -d 1 # print just level 1

NOTE: echo * => list directories and files of actual directory
```

### crontab

[blog desde linux - crontab](https://blog.desdelinux.net/cron-crontab-explicados/)



### stat
Information of a File
```
stat file1
```

### zip
```
zip -r folders.zip images
unzip folders.zip -d <directory>
zipinfo folders.zip
```


### find
- [Cheatsheet - devhints](https://devhints.io/find)

```

find . -mtime +5 # 5 days modified time

find . -iname 'archivo*' # case insensitive by name

find . -name 'archivo*' # case insensitive

find . -name 'archivo*' --delete # case insensitive and delete USE AT YOUR OWN RISK
```

### cal and date
- [tutorialkart - date](https://www.tutorialkart.com/bash-shell-scripting/bash-date-format-options-examples/)
date 

date 
date -d "+7 days"
date -d "+2 weeks"

cal
cal 11 20

### bc 
bc # is a calculator

### ps

ps -ejH ## print a process tree
ps fax # DASCII art process hierarchy (forest)(f),  Select all processes except both session leaders

kill <pid>
killall <process-name> # when a process has the same names

### curl

curl ifconfig.me

### cat

cat file
less file
tail file

### grep
- [dev-notes - grep](https://dev-notes.eu/2016/10/grep-commands-cheatsheet/)
- [ryanstutorials](https://ryanstutorials.net/linuxtutorial/cheatsheetgrep.php) :star:

grep -i juan file # search word "juan" insensitive on file
grep -w juan file # search whole word "juan" on file
grep -v juan file # lines that not match the pattern
grep -ic juan file # counts of matches
grep -il juan file # prints the file which match the pattern
grep -in juan file # prints line which matches the pattern
 

### df

df -h # report file system disk space usage in a human readable way