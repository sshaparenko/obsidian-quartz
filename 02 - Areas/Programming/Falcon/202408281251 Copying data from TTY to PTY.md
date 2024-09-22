---
date: 2024-08-28T12:51
tags: []
---


```go
ptmx, err := os.OpenFile("/dev/pts/3", os.O_RDONLY, fs.FileMode(os.O_RDONLY))

if err != nil {
	log.Fatalf("Failed to open the tty device: %s\n", err.Error())
}

cmd.Stdin = ptmx
cmd.Stdout = ptmx
cmd.Stderr = ptmx

pty, err := pty.Start(cmd)
if err != nil {
	log.Fatalf("Failed to start a subshell process: %s\n", err.Error())
}

defer pty.Close()
defer ptmx.Close()

go func() {
	w, err := io.Copy(cmd.Stdout, pty)
	if err != nil {
		log.Fatalf("Failed to copy output: %s\n", err.Error())
	}
	fmt.Println(w)
}()

go func() {
	w, err := io.Copy(pty, cmd.Stdin)
	if err != nil {
		log.Fatalf("Failed to copy input: %s\n", err.Error())
	}
	fmt.Println(w)
}()
```