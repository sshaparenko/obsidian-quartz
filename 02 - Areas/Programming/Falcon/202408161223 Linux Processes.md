---
date: 2024-08-16T12:23
tags:
  - linux
cssclasses:
  - center-images
  - page-grid
---
## Processes
Linux process can be in one of the following state:
- R - running or runnable (on run queue)
- D - Uninterruptible sleep (waiting for some event)
- S - Interruptible sleep (waiting for some event or signal)
- T - stopped, either by a job control signal or because it is being traced by a debugger
- Z - zombie process, terminated but not yet reaped by its parent 

![[Pasted image 20240816122659.png]]

> Use `ps l` to see all the processes running with the detailed information

