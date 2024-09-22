---
date: 2024-08-27T12:47
tags:
  - linux
  - falcon
---
### How `script` works?
1. **Starts a Subshell:** When you run `script` command its starts a new subshell. This subshell acts as an intermediary between your terminal and commands you run
2. **Captures input and output:** The `script` command uses pty to capture input and output that pass through the terminal and writes all into a file
3. **PTY:** `script` relies on the pty subsystem in Linux. A pty provides mechanism that emulates a terminal, enabling the `script` command to capture the interaction between your terminal and the shell. The pty acts as a bridge between the terminal and the shell.

