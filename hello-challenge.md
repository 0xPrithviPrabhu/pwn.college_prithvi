# Intro to Commands (hello)

This is the first introductory challenge on pwn.college. The goal is to set up SSH key-based authentication, connect to the remote challenge server, and run a specific command (`hello`) to retrieve the flag.

---
## My solve

**flag:** pwn.college{83hSNyNCGA2i9kkZ4ce1YFCkmW_.QX3YjM1wSM1kjNzEzW}

The solution process involved setting up an SSH key, adding it to my pwn.college account, and then using it to connect to the server and run the required command.

 1. Generate SSH Key Pair

First, I created an SSH key pair on my local machine using the `ssh-keygen` command.

```bash
$ ssh-keygen -t ed25519 -f ./key -N ''
Generating public/private ed25519 key pair.
...

2. Add Public Key to pwn.college
Next, I displayed the content of the public key file (key.pub) and copied it.

Bash

$ cat key.pub
ssh-ed25519 AAAAC3Nz...
I then navigated to the pwn.college User Settings page and pasted this public key to register it with my account.

3. Connect and Get Flag
With my key authorized, I first had to start the challenge on the website. After clicking the "Start" button, I could SSH into the challenge server using my private key.

Bash

$ ssh -i key hacker@dojo.pwn.college
Welcome (hello) to intro-to-commands!
hacker@hello-intro-to-commands:$
Once connected, I ran the hello command as instructed by the challenge prompt, which printed the flag to the terminal.

Bash

hacker@hello-intro-to-commands:$ hello
pwn.college{83hSNyNCGA2i9kkZ4ce1YFCkmW_.QX3YjM1wSM1kjNzEzW}

What I learned (optional)
This challenge was a practical introduction to the full workflow of SSH key-based authentication on a CTF platform. I learned how to generate keys, use the public vs. private key

