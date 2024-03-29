# Task 2 - `stracing` the `echo` command.

## 1. Stracing

Execute this to strace the command `echo hello`, and save the syscall log to a file called `trace`.

```
$ strace -o trace echo hello
```

## 2. A note on dynamic linking

`/bin/echo` is a dynamically linked program, so it will load libraries it depends on before starting. You will see this in strace!

You can confirm that it is for yourself - and identify which libraries you should see it accessing in strace - by running this command:

```
$ ldd /bin/echo                                                 
        linux-vdso.so.1 (0x0000ffffa0dbc000)
        libc.so.6 => /lib64/libc.so.6 (0x0000ffffa0b30000)
        /lib/ld-linux-aarch64.so.1 (0x0000ffffa0d74000)
```

## 3. Analyzing the output of strace

_Tip:_ use a whiteboard, a piece of paper, or just open the `trace` file in a graphical editor and write your thoughts/guesses for syscalls there.

The goal of this task is to be able to explain to your tutor the purpose of every line in the strace log.

## Next

Next task: [./task4-strace-curl.md](./task4-strace-curl.md)
