# Challenge Name
Finding and reading hidden file.

## My solve
**Flag:** `pwn.college{EL3edJO1X7kIfZu0KBwZqAZfFZG.QXwUDO0wSM1kjNzEzW}`

They showed me how to get list of hidden files and hence using that found file which had flag and used the cat command to read the file

```
hacker@commands~hidden-files:/$ ls -a
.   .dockerenv            bin   challenge  etc   lib    lib64   media  nix  proc  run   srv  tmp  var
..  .flag-20500332520053  boot  dev        home  lib32  libx32  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:/$ cat .flag-20500332520053 
pwn.college{EL3edJO1X7kIfZu0KBwZqAZfFZG.QXwUDO0wSM1kjNzEzW}
```

## What I learned (optional)
How to find and open hidden file.

## Incorrect tangents (optional)
NA

## References (optional)
NA
