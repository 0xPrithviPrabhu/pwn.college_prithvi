# Challenge Name
This challenge was about finding and running a program with a randomized name inside a specific directory.

## My solve
**Flag:** `pwn.college{0xzGK_XExgQHswHKkzLdqKpJ5zz.QX4IDO0wSM1kjNzEzW}`

My thought process was that since I didn't know the program's name, my first step had to be discovering it.

I used the ls command on the /challenge directory to list its contents. This revealed the randomly named executable file. Once I had the exact filename, I could then run the program using its full absolute path to get the flag.

```
hacker@commands~listing-files:~$ ls /challenge/
2306-renamed-run-933  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/2306-renamed-run-933 
Yahaha, you found me! Here is your flag:
pwn.college{0xzGK_XExgQHswHKkzLdqKpJ5zz.QX4IDO0wSM1kjNzEzW}
```

## What I learned (optional)
This challenge showed me a practical, two-step problem-solving process: first, use a discovery command like ls to gather information, and then use that new information to execute the next command.

## Incorrect tangents (optional)
NA

## References (optional)
NA
