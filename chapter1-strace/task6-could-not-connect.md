# Task 6 - what are you trying to connect to?

Execute this command to compile our program (no peeking what it does! it's intentionally mangled here):

```bash
echo 'I2luY2x1ZGUgPHN0ZGlvLmg+CiNpbmNsdWRlIDx1bmlzdGQuaD4KI2luY2x1ZGUgPHN0ZGxpYi5oPgojaW5jbHVkZSA8c3lzL3NvY2tldC5oPgojaW5jbHVkZSA8bmV0aW5ldC9pbi5oPgojaW5jbHVkZSA8YXJwYS9pbmV0Lmg+CiNpbmNsdWRlIDxzeXMvdHlwZXMuaD4KI2luY2x1ZGUgPHN5cy9zb2NrZXQuaD4KI2luY2x1ZGUgPG5ldGRiLmg+CgppbnQgbWFpbihpbnQgYXJnYywgY2hhciAqYXJndltdKQp7CiAgICBzdHJ1Y3QgYWRkcmluZm8gaGludHMgPSB7fSwgKmFkZHJzOwogICAgaW50IGVyciA9IGdldGFkZHJpbmZvKCJ3cm9uZy5nb29nbGUuY29tIiwgIjgwIiwgJmhpbnRzLCAmYWRkcnMpOwogICAgaWYgKGVyciAhPSAwKQogICAgewogICAgICAgIGZwcmludGYoc3RkZXJyLCAiJXM6ICVzXG4iLCBhcmd2WzBdLCBnYWlfc3RyZXJyb3IoZXJyKSk7CiAgICAgICAgYWJvcnQoKTsKICAgIH0gZWxzZSB7CglwdXRzKCJPSyEiKTsKICAgIH0KfQo=' | base64 -d | gcc -x c -o client -
```

Execute this program and see what's going on. What is it actually trying to connect to? Let's find out!

Tip: Try both `strace` and a new tool `ltrace` here. `ltrace` inject itself between your traced program and dynamically loaded libraries, to tell you what's being invoked from dynamically linked libraries.
