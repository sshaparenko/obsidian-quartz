---
date: 2024-08-20T15:02
tags:
  - linux
  - falcon
  - unix
---
A socket in Linux is a **bidirectional communication pipe**.

Lets use `netcat` **to create a Unix Socket**. `netcat` can be used for many tasks involving networking in Linux.

```bash
nc -U /tmp/demo.sock -l
```

The `-U` parameter tells netcat to **use Unix Socket file**. `-l` tells it to **act as server-side** and listen to the specified socket for incoming connections

**To inspect the file created** by netcat let’s use `lsof`. 

`lsof` command is a utility used to list and give information about 
files that are in use by processes.

```bash
lsof /tmp/demo.sock
```

```bash
COMMAND PID    USER   FD   TYPE       DEVICE   SIZE/OFF  NODE    NAME
nc 121737 sshaparenkos 3u  unix 0x0000000000000000 0t0 301459 /tmp/demo.sock
type=STREAM
```

`FD` stands for file descriptor.

**When Linux process need to perform I/O operations, they do so by reading or writing to file descriptors**

### Socket Types


