# Challenge Name
Challenge is above moving one file to another

## My solve
**Flag:** `pwn.college{kKDln1UWmn2Ac49Snln71EXP9Xt.0VOxEzNxwSM1kjNzEzW}`

They showed that with mv I could move one file content to other and using that knowledge i did the same I wrote mv file 1 file 2 and boom it worked


```
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ ls
f  flag
hacker@commands~moving-files:~$ /challenge/check 
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{kKDln1UWmn2Ac49Snln71EXP9Xt.0VOxEzNxwSM1kjNzEzW}

```

## What I learned (optional)
How to move a file

## Incorrect tangents (optional)
NA

## References (optional)
NA
