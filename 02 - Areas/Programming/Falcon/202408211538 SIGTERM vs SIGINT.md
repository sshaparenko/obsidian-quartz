---
date: 2024-08-21T15:38
tags:
  - linux
  - unix
---
`SIGINT` is a signal used to request a graceful termination of a process, typically initiated by the user. 

`SIGTERM` is a signal used to request a process to terminate gracefully, which can be sent by other processes or system itself.

**Processing those signal is crucial in providing a graceful program termination.**

Here is an example of graceful termination in Go

```go
func main(){
	c := make(chan os.Signal, 1)
	signal.Notify(c, os.Interrupt, syscall.SIGTERM)
	
	go func(){
	  <-ch
	  os.Remove("/tmp/falcon.sock")
	  os.Exit(1)
	}()
}
```