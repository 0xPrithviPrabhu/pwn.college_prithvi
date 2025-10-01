# Challenge Name
Big practice of cd,ls,cat commands

## My solve
**Flag:** `pwn.college{8JUtiCBEUDfsYGke2jYZQgNWe7u.QX5IDO0wSM1kjNzEzW}`

All I did was practice as I already know ls,cd and cat does

```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls -a
.   .dockerenv  bin   challenge  etc   home  lib32  libx32  mnt  opt   root  sbin  sys  usr
..  MESSAGE     boot  dev        flag  lib   lib64  media   nix  proc  run   srv   tmp  var
hacker@commands~an-epic-filesystem-quest:/$ cat MESSAGE 
Great sleuthing!
The next clue is in: /usr/lib/python3/dist-packages/parso/python

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/python3/dist-packages/parso/python
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/parso/python$ ls -a
.   .SPOILER     __pycache__  errors.py      grammar27.txt  grammar34.txt  grammar36.txt  grammar38.txt  parser.py  prefix.py  tokenize.py
..  __init__.py  diff.py      grammar26.txt  grammar33.txt  grammar35.txt  grammar37.txt  grammar39.txt  pep8.py    token.py   tree.py
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/parso/python$ cat .SPOILER 
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/platformdirs-4.3.6.dist-info/licenses

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/parso/python$ cd /usr/local/lib/python3.8/dist-packages/platformdirs-4.3.6.dist-info/licenses
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/platformdirs-4.3.6.dist-info/licenses$ ls -a
.  ..  INSIGHT  LICENSE
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/platformdirs-4.3.6.dist-info/licenses$ cat INSIGHT 
Tubular find!
The next clue is in: /opt/linux/linux-5.4/drivers/dma/xilinx

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/platformdirs-4.3.6.dist-info/licenses$ cd /opt/linux/linux-5.4/drivers/dma/xilinx
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/dma/xilinx$ ls -a
.  ..  .SNIPPET  .built-in.a.cmd  Makefile  built-in.a  xilinx_dma.c  zynqmp_dma.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/dma/xilinx$ cat .SNIPPET 
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/dma/xilinx$ cd /usr/local/lib/python3.8/dist-packages/an
angr/                   angr-9.2.102.dist-info/ anyio/                  anyio-4.5.2.dist-info/  
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/dma/xilinx$ cd /usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap$ ls
CUE  __init__.py  __pycache__  heap_base.py  heap_brk.py  heap_freelist.py  heap_libc.py  heap_ptmalloc.py  utils.py
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap$ cat CUE 
Yahaha, you found me!
The next clue is in: /usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/state_plugins/heap$ cd /usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ ls
EVIDENCE  LC_MESSAGES
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ cat EVIDENCE 
Yahaha, you found me!
The next clue is in: /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers
bash: /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers: Is a directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ ls /usr/lib/llvm-10/lib/clang/10.0.0/include
/openmp_wrappers
BLUEPRINT-TRAPPED  __clang_openmp_math.h  __clang_openmp_math_declares.h  cmath  math.h
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ cat BLUEPRINT-TRAPPED
cat: BLUEPRINT-TRAPPED: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ ls /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers -A
BLUEPRINT-TRAPPED  __clang_openmp_math.h  __clang_openmp_math_declares.h  cmath  math.h
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ ls /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers -a
.  ..  BLUEPRINT-TRAPPED  __clang_openmp_math.h  __clang_openmp_math_declares.h  cmath  math.h
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ ls /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers/BLUEPRINT-TRAPPED 
/usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers/BLUEPRINT-TRAPPED
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ '
> 
> cd /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers/BLUEPRINT-TRAPPED 
> 
> 
> /
> .
> '
bash: 

cd /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers/BLUEPRINT-TRAPPED 


/
.
: No such file or directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ cd /usr/lib/llvm-10/lib/clang/10.0.0/include
/openmp_wrappers/BLUEPRINT-TRAPPED 
bash: cd: /usr/lib/llvm-10/lib/clang/10.0.0/include/openmp_wrappers/BLUEPRINT-TRAPPED: Not a directory
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ cat /usr/lib/llvm-10/lib/clang/10.0.0/includ
e/openmp_wrappers/BLUEPRINT-TRAPPED 
Tubular find!
The next clue is in: /usr/lib/python3/dist-packages/sphinx/ext/__pycache__

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/plumbum/cli/i18n/ru$ cd /usr/lib/python3/dist-packages/sphinx/ext/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sphinx/ext/__pycache__$ ls
REVELATION                       doctest.cpython-38.pyc      imgconverter.cpython-38.pyc         linkcode.cpython-38.pyc
__init__.cpython-38.pyc          extlinks.cpython-38.pyc     imgmath.cpython-38.pyc              mathbase.cpython-38.pyc
apidoc.cpython-38.pyc            githubpages.cpython-38.pyc  inheritance_diagram.cpython-38.pyc  mathjax.cpython-38.pyc
autosectionlabel.cpython-38.pyc  graphviz.cpython-38.pyc     intersphinx.cpython-38.pyc          todo.cpython-38.pyc
coverage.cpython-38.pyc          ifconfig.cpython-38.pyc     jsmath.cpython-38.pyc               viewcode.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sphinx/ext/__pycache__$ cat REVELATION 
Yahaha, you found me!
The next clue is in: /opt/linux/linux-5.4/include/config/thread
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3/dist-packages/sphinx/ext/__pycache__$ cd /opt/linux/linux-5.4/include/config/thread
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/thread$ ls 
TEASER  info
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/include/config/thread$ cat TEASER 
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{8JUtiCBEUDfsYGke2jYZQgNWe7u.QX5IDO0wSM1kjNzEzW}
```

## What I learned (optional)
More of learnt I practiced 

## Incorrect tangents (optional)
NA

## References (optional)
NA
