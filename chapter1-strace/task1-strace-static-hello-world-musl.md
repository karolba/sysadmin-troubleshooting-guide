# Task 1 - `stracing` a static hello world program compiled with musl libc

## 1. Compiling a program to strace

We'll be tracing the following program:

```c
#include <stdio.h>
int main() { puts("Hello world"); }
```

Execute this to compile the C program into `./hello-static`:

```bash
$ echo -e '#include <stdio.h>\nint main() { puts("Hello world"); }' | musl-gcc -x c - -static -o hello-musl
```

## 2. Stracing

```
$ strace ./hello-musl
```

the output on screen will be an interleave of our "hello world" message, and output of strace. To actually properly see the output of strace, either tell strace to save its logs to a file (`strace -o output-file-name ./hello-musl`) or silece the output of `./hello-static` (`strace ./hello-static >/dev/null`).

## 3. Analyzing the output of strace

This is the output I get from strace on an ARM laptop running Linux from 2023:

```
execve("./hello-musl", ["./hello-musl"], 0xffffd9c33130 /* 104 vars */) = 0
set_tid_address(0x440750)               = 13718
ioctl(1, TIOCGWINSZ, 0xffffc7163610)    = -1 ENOTTY (Inappropriate ioctl for device)
writev(1, [{iov_base="Hello world", iov_len=11}, {iov_base="\n", iov_len=1}], 2) = 12
exit_group(0)                           = ?
+++ exited with 0 +++
```

You should be seeing something similar by now - a list of syscalls the `./hello-static` program made to the Linux kernel.
Your task is now to annotate the output, to gain understanding of what each of these syscalls is more-or-less for, and why the `./hello-static` binary might have invoked each of them.
This can involve guessing.

Helpful resources:

1. The second chapters of `man`uals describes system calls. You can view a manual for every syscall with `man 2 syscall-name` (for example `man 2 execve`)
2. Just google for an explanation of what the syscall is used for. The `man`uals can get very technical and _might not be perfect_ for getting a general explanation.

The goal of this task is to be able to explain to your tutor the purpose of every line in the strace log.

## Next

Next task: [./task2-strace-busybox-echo-hello.md](./task2-strace-busybox-echo-hello.md)
