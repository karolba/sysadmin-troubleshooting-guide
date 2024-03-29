# Task 2 - `stracing` curl

## 1. Stracing

```
$ strace -o trace curl http://google.com
```

## 2. Filtering out memory-management related syscalls

Add the `-e trace='!memory'` argument to strace to get rid of memory-related syscalls from the outputs. Observe how the log becomes less cluttered!

## 3. Keeping track of file descriptors

Add the `-yy` flag to strace to contextualize file descriptors, whenever they appear. In another words, the `-yy` flag will turn this:

```
close(3) = 0
```

into this:

```
close(3</usr/lib64/libkeyutils.so.1.9>) = 0
```

Apply the `-yy` flag yourself and compare the output visually (look for added `<>` angled brackets).

## 4. Analyzing the output of strace

The goal of this task is to be able to explain to your tutor the purpose of every line in the strace log.

## Next

Work in progress - to be announced!
