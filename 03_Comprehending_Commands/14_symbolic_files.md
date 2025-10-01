# Challenge Name
This challenge was a puzzle about tricking a program. The program was hardcoded to read a fake flag from /home/hacker/not-the-flag, but the real flag was at /flag.

## My solve
**Flag:** `pwn.college{0wFwvSsdykIUjHiaLkt2PhV_vmB.QX5ETN1wSM1kjNzEzW}`

My thought process was that if I couldn't change the program, I had to change the file it was looking at. This called for a "bait and switch" using a symbolic link.

First, I had to remove the original decoy file to clear the path. Then, I created a symbolic link (ln -s) at the decoy's location (/home/hacker/not-the-flag) that pointed to the real flag's location (/flag). When I ran the program again, it followed my link to the real flag without ever knowing it was tricked.


```
hacker@commands~linking-files:~$ ln -s /challenge/catflag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ cd ~/not-the-flag 
bash: cd: /home/hacker/not-the-flag: Not a directory
hacker@commands~linking-files:~$ file /challenge/catflag 
/challenge/catflag: setuid a /opt/pwn.college/bash script, ASCII text executable
hacker@commands~linking-files:~$ cat /challenge/catflag 
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:~$ cat ~/catflag
cat: /home/hacker/catflag: No such file or directory
hacker@commands~linking-files:~$ cat ~/not-the-flag 
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag 
About to read out the /home/hacker/not-the-flag file!
pwn.college{0wFwvSsdykIUjHiaLkt2PhV_vmB.QX5ETN1wSM1kjNzEzW}
```

## What I learned (optional)
This challenge was a brilliant lesson on the power of symbolic links. It taught me they aren't just shortcuts, but powerful tools for redirecting programs and manipulating the filesystem to solve complex problems.

## Incorrect tangents (optional)
na
## References (optional)
NA
