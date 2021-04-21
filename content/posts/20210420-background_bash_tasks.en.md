+++ 
draft = false
date = 2021-04-20T23:54:03-03:00
title = "Bash commands to execute tasks on background"
description = ""
slug = ""
authors = []
tags = ["linux", "bash", "commands", "background"]
categories = ["linux"]
externalLink = ""
series = []
+++

Process start in the background, but it is still connected with the terminal
(if you close the terminal, the process will be terminated)

```
<command> & 
```

Actually, above command continues printing on the shell...
To avoid that behavior, we could redirect the standard output

```
<command>  &>/dev/null &
# it is redirecting both, STDOUT and STDERR to /dev/null
```

Remember, we could also use streams =>  STDIN, STDOUT & STDERR (0, 1 & 2)

To disconnect a job from the current shell:

```
disown [options] jobID1 jobID2 ... jobIDN
```

_________

If you need to close de current shell terminal, use "nohup" command: 

```
nohup <command> &>/dev/null &
```

Also, we could use disown with -h flag:

```
disown -h jobID
disown -h %1
```

Jobs ids are obtained from: 

```
jobs -l
```



Refs:
- https://phoenixnap.com/kb/disown-command-linux
- https://www.howtogeek.com/435903/what-are-stdin-stdout-and-stderr-on-linux/#
- https://blog.desdelinux.net/que-es-devnull-y-como-puede-ayudarte/ 
- https://vidatecno.net/ejecutar-comandos-bash-en-segundo-plano-de-la-manera-correctalinux/
