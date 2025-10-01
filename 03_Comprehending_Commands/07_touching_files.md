# Challenge Name
This challenge required me to create a new, empty file with a specific name given by the program.

## My solve
**Flag:** `pwn.college{kNi8ev4DaAS4JsEwPUSz4xsfnHJ.QXwMDO0wSM1kjNzEzW}`

My thought process was that I needed the most direct command for creating a new file. The touch command is designed for exactly this purpose.

I used touch followed by the filename provided by the challenge. To confirm it worked, I immediately ran ls to see the new file listed in the directory.

```
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  tmp.4mK6TfTSUV
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ ls
bin  hsperfdata_root  pwn  tmp.4mK6TfTSUV
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.4mK6TfTSUV
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{kNi8ev4DaAS4JsEwPUSz4xsfnHJ.QXwMDO0wSM1kjNzEzW}
hacker@commands~touching-files:/tmp$ 
```

## What I learned (optional)
This challenge solidified that touch is the standard, most efficient command for creating new, empty files.

## Incorrect tangents (optional)
NA

## References (optional)
NA
