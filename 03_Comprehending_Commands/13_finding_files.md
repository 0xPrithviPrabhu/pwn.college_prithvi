# Challenge Name
Finding files

## My solve
**Flag:** `pwn.college{kmQ0vbPnr79tzYZ8rPWx5v8hFHO.QXyMDO0wSM1kjNzEzW}`

They told I could find files etc using file command and hence I used it and used contraint name which I gave as flag anf then one by one checked the flag

```
Bhacker@commands~finding-filesfind / -name flag
/home/hacker/flag
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/doc/libpython3.8-minimal/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /home/hacker/flag
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
hacker@commands~finding-files:~$ /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ ls /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
__init__.py  __pycache__  flag.py
hacker@commands~finding-files:~$ ls /usr/local/lib/python3.8/dist-packages/pwnlib/flag
__init__.py  __pycache__  flag.py
hacker@commands~finding-files:~$ cd /usr/local/lib/python3.8/dist-packages/pwnlib/flag
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cat flag.py 
"""Describes a way to submit a key to a key server.
"""
from __future__ import absolute_import
from __future__ import division

import os

from pwnlib.args import args
from pwnlib.log import getLogger
from pwnlib.tubes.remote import remote

env_server  = args.get('FLAG_HOST', 'flag-submission-server').strip()
env_port    = args.get('FLAG_PORT', '31337').strip()
env_file    = args.get('FLAG_FILE', '/does/not/exist').strip()
env_exploit_name = args.get('EXPLOIT_NAME', 'unnamed-exploit').strip()
env_target_host  = args.get('TARGET_HOST', 'unknown-target').strip()
env_team_name    = args.get('TEAM_NAME', 'unknown-team').strip()

log = getLogger(__name__)

def submit_flag(flag,
                exploit=env_exploit_name,
                target=env_target_host,
                server=env_server,
                port=env_port,
                team=env_team_name):
    """
    Submits a flag to the game server

    Arguments:
        flag(str): The flag to submit.
        exploit(str): Exploit identifier, optional
        target(str): Target identifier, optional
        server(str): Flag server host name, optional
        port(int): Flag server port, optional
        team(str): Team identifier, optional

    Optional arguments are inferred from the environment,
    or omitted if none is set.

    Returns:
        A string indicating the status of the key submission,
        or an error code.

    Doctest:

        >>> l = listen()
        >>> _ = submit_flag('flag', server='localhost', port=l.lport)
        >>> c = l.wait_for_connection()
        >>> c.recvall().split()
        [b'flag', b'unnamed-exploit', b'unknown-target', b'unknown-team']
    """
    flag = flag.strip()

    log.success("Flag: %r" % flag)

    data = "\n".join([flag,
                      exploit,
                      target,
                      team,
                      '']).encode('ascii')

    if os.path.exists(env_file):
        write(env_file, data)
        return

    try:
        with remote(server, int(port)) as r:
            r.send(data)
            return r.recvall(timeout=1)
    except Exception:
        log.warn("Could not submit flag %r to %s:%s", flag, server, port)
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cat  /home/hacker/flag
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
hacker@commands~finding-files:/usr/local/lib/python3.8/dist-packages/pwnlib/flag$ cd
hacker@commands~finding-files:~$ cat  /home/hacker/flag
pwn.college{4EsPxT8Q5c5rKyz97KjihNBDf64.QXxcTN0wSM1kjNzEzW}
hacker@commands~finding-files:~$ ls /home/hacker/flag
/home/hacker/flag
hacker@commands~finding-files:~$  /home/hacker/flag
bash: /home/hacker/flag: Permission denied
hacker@commands~finding-files:~$ cd /usr/share/doc/libpython3.8
libpython3.8/         libpython3.8-dev/     libpython3.8-minimal/ libpython3.8-stdlib/  
hacker@commands~finding-files:~$ cd /usr/share/doc/libpython3.8-minimal
hacker@commands~finding-files:/usr/share/doc/libpython3.8-minimal$ cat flag 
pwn.college{kmQ0vbPnr79tzYZ8rPWx5v8hFHO.QXyMDO0wSM1kjNzEzW}hacker@commands~finding-files:/usr/share/doc/libpython3.8-minimal$ 
```

## What I learned (optional)
How to find files using files and how to find files using their names.

## Incorrect tangents (optional)
NA.

## References (optional)
NA.
