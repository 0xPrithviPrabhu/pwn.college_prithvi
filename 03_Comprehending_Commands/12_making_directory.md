# Challenge Name
To make directory inside tmp directory and save or create a file called college.

## My solve
**Flag:** `pwn.college{oQmx3lUMS9EZSok00MHe3P67pPf.QXxMDO0wSM1kjNzEzW}`

They explained that mkdir makes a directory and touch make a file hence used them to solve this one

```
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.4mK6TfTSUV
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{oQmx3lUMS9EZSok00MHe3P67pPf.QXxMDO0wSM1kjNzEzW}
```

## What I learned (optional)
How to make directories using mkdir command

## Incorrect tangents (optional)
NA

## References (optional)
NA
