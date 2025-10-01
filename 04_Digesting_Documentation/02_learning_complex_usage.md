# Challenge Name
This challenge was about understanding that command-line arguments can themselves require their own arguments.

## My solve
**Flag:** `pwn.college{kD5sfCtZxlHlm1sDKOR2MDehTrR.QX1ITO0wSM1kjNzEzW}`

My thought process was to follow the documentation, but my first attempt failed. The key was reading the error message carefully.

The documentation said to use the --printfile argument. When I tried that alone, the program told me, "You must pass a file for --printfile to read!" This made me realize that --printfile needed a value. I provided the standard path to the flag, /flag, as the second argument, which solved the challenge.


```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag 
Correct argument! Here is the /flag file:
pwn.college{kD5sfCtZxlHlm1sDKOR2MDehTrR.QX1ITO0wSM1kjNzEzW}
hacker@man~learning-complex-usage:~$ 
```

## What I learned (optional)
This was a great lesson in reading error messages. They often tell you exactly what you're missing. I learned that arguments like --printfile aren't just on/off switches; they often need a specific input to function correctly.

## Incorrect tangents (optional)
NA

## References (optional)
NA
