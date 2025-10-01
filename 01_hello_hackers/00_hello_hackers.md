# Challenge Name: The Root
The goal of this challenge was to run a program located in the root directory (/).

# My solve
**Flag**:`` pwn.college{83hSNyNCGA2i9kkZ4ce1YFCkmW_.QX3YjM1wSM1kjNzEzW}``

My thought process was that since just typing pwn didn't work, the program wasn't in a standard system path. I needed to tell the shell its exact location.

The challenge name and prompt hinted the program was in the root directory.

To run a program from the root, you need an absolute path, which always starts with /. This led me to the correct command.
```
$ /pwn
BOOM!!!
Here is your flag:
pwn.college{83hSNyNCGA2i9kkZ4ce1YFCkmW_.QX3YjM1wSM1kjNzEzW}
```

## What I learned
This challenge taught me how to use absolute paths to execute programs that aren't in the default $PATH.

## Incorrect tangents
N/A

## References
N/A
