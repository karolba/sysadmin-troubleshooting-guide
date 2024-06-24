# Task 5 - figuring out where does `bash` search for config files

## 1. Stracing

```
$ strace -o trace bash -l -c ''
```

## 2. Filtering out stuff

Feel free to analyze the manpage of `strace` itself to be able to filter out unneeded trace lines

## 3. Analyzing the output of strace

The goal of this task is to be able to figure out from where does bash really read its config.

## Next

To be announced
