# Challenge Name
This challenge introduced the grep command. The goal was to find a specific line containing the word "flag" inside a large file that would be tedious to read manually.

## My solve
**Flag:** `pwn.college{EUprTcnG38xVNwxBI1lvphs3Am_.QX3EDO0wSM1kjNzEzW}`

My thought process was that manually reading a huge dictionary file was not a viable option. I needed a command that could search the file's contents for me.

The grep command is the standard tool for this. I used it to search for the pattern "flag" inside the /usr/share/dict/words file, which immediately found and displayed the correct line containing the flag.

```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{EUprTcnG38xVNwxBI1lvphs3Am_.QX3EDO0wSM1kjNzEzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ 
```

## What I learned 
This challenge was a fantastic introduction to grep, teaching me that it's the essential tool for quickly searching for specific text within files, saving a massive amount of time.

## Incorrect tangents 
NA

## References 
NA
