# Task 2 - `stracing` the `busybox echo` command.

## 1. Stracing

Execute this to strace the command `busybox echo hello`, and save the syscall log to a file called `trace`.

```
$ strace -o trace busybox echo hello
```

## 2. Analyzing the output of strace

_Tip:_ use a whiteboard, a piece of paper, or just open the `trace` file in a graphical editor and write your thoughts/guesses for syscalls there.

The goal of this task is to be able to explain to your tutor the purpose of every line in the strace log.

## Next

Next task: [./task3-strace-gnu-echo.md](./task3-strace-gnu-echo.md)
