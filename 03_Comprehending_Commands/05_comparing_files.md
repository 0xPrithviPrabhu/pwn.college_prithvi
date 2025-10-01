# Challenge Name
This challenge was about finding the single difference between two files that were almost identical.

## My solve
**Flag:** `pwn.college{wNyskOjVuPLMC3NMNkj6LW0HlMK.01MwMDOxwSM1kjNzEzW}`

My thought process was that reading both files and comparing them line-by-line would be slow and prone to error. I needed a command that could automate this comparison for me.

The diff command is designed for this exact purpose. I provided it with the paths to both files. The command's output, 44a45, told me that the second file had an added line at position 45 that wasn't in the first file, and it printed that unique line, which was the flag.

```
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt 
44a45
> pwn.college{wNyskOjVuPLMC3NMNkj6LW0HlMK.01MwMDOxwSM1kjNzEzW}

```


## What I learned (optional)
This challenge taught me the power of the diff command. It's an incredibly efficient tool for instantly finding differences between two files, which is much faster and more reliable than manual comparison.

## Incorrect tangents (optional)
NA

## References (optional)
NA
