---
date: 2024-08-27T16:33
tags: []
---
**By manipulating file descriptors, you can redirect input and output from one shell to another**

File Descriptor Path: `/proc/PID/fd`

`/proc/PID/fd/N` is a symbolic link, that points to the terminal device in `/dev/pts/N` that the process is using as `stdin`, `stdout` or `stderr`

><u>for unix.Dup2 I need fd int value. It's an fd of tty associated with particular terminal session. So to get this fd number, I should get tty value from terminal stats, then map it to a device file, open device file with os.Open and get the fd?</u>
### File Descriptors
File descriptors (FDs) are part of POSIX API and use basic integers to determine state. An FD acts as a handle used to access an IO resource or any file resource at the kernel level. These file resources can range from sockets, terminals, pipes, devices and regular files. 

In most cases, when a call to `open()` or `creat()` is made by an interactive terminal, the calling process inherits three open file descriptors that are supported by the terminal. These are small integers that are typically non-negative and small in size.

In UNIX 
- 0 - represents `stdin`
- 1 - represents `stdout`
- 2 - represents `stderr`