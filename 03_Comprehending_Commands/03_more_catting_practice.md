# Challenge Name
This challenge was about using cat to read a file with a very long absolute path without being able to use cd.

## My solve
**Flag:** `pwn.college{46fUzFK4bKh_gH-cE_QWLyJ4bkK.QXwITO0wSM1kjNzEzW}`

My thought process was that typing the long path by hand would lead to typos. After my initial attempts failed, I realized the most efficient and error-proof method was to use Tab Completion.

I built the command by typing the first few letters of each directory in the path and pressing Tab to let the shell auto-complete the rest. This ensured the path was 100% correct.

```
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /lib/x86_64-linux-gnu/apr-util-1/flag. Go cat it out **without** 
cding into that directory!
hacker@commands~more-catting-practice:~$ cat flag /lib/x86_64-linnux-gnu/apr-util-1
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
cat: /lib/x86_64-linnux-gnu/apr-util-1: No such file or directory
hacker@commands~more-catting-practice:~$ cat flag /lib/x86_64-linnux-gnu/apr-util-1/
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
cat: /lib/x86_64-linnux-gnu/apr-util-1/: No such file or directory
hacker@commands~more-catting-practice:~$ cat flag ./
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
cat: ./: Is a directory
hacker@commands~more-catting-practice:~$  /lib/x86_64-linnux-gnu/apr-util-1
bash: /lib/x86_64-linnux-gnu/apr-util-1: No such file or directory
hacker@commands~more-catting-practice:~$ /lib
bash: /lib: Is a directory
hacker@commands~more-catting-practice:~$ cat flag /lib/x86_64-linnux-gnu/apr-util-1/flag
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
cat: /lib/x86_64-linnux-gnu/apr-util-1/flag: No such file or directory
hacker@commands~more-catting-practice:~$ cat /lib/x86_64-linux-gnu/apr-util-1/flag 
pwn.college{46fUzFK4bKh_gH-cE_QWLyJ4bkK.QXwITO0wSM1kjNzEzW} 
```
![Screenshot for challenge 3](02_more_catting_practice.png)

## What I learned (optional)
This challenge was a crucial lesson in using Tab Completion to avoid errors and work faster when dealing with long file paths.

## Incorrect tangents (optional)
My first attempts involved trying to type the entire path by hand. This was my incorrect tangent. As predicted, I made small typos, which led to "No such file or directory" errors. This immediate negative feedback was the key clue that my manual approach was flawed and that I needed a more robust, automated method like Tab Completion to solve the challenge.

## References (optional)
nothing apart from what was given in the website
