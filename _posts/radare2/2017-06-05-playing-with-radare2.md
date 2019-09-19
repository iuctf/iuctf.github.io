---
layout: blog
title:  "Playing with radare2"
date:   2017-06-05 18:48:20 -0400
category: radare2
meta: Playing with radare2 to dig into the CMU Bombs.
folder: radare2
---
## Playing with radare2 to dig into the CMU Bombs

We try to crack the cyber security bombs posted on CMU by using radare2.
* [http://csapp.cs.cmu.edu/3e/labs.htm](http://csapp.cs.cmu.edu/3e/labs.html)
* [https://radare.gitbooks.io/radare2book/content/refcard/intro.html](https://radare.gitbooks.io/radare2book/content/refcard/intro.html) 

1. Inspect the binary code in brief
```bash
[18:45] CREST-MacBook-Pro-2: bomb $ rabin2 -I bomb
arch     x86
binsz    26406
bintype  elf
bits     64
canary   true
class    ELF64
crypto   false
endian   little
havecode true
intrp    /lib64/ld-linux-x86-64.so.2
lang     c
linenum  true
lsyms    true
machine  AMD x86-64 architecture
maxopsz  16
minopsz  1
nx       true
os       linux
pcalign  0
pic      false
relocs   true
relro    partial relro
rpath    NONE
static   false
stripped false
subsys   linux
va       true
[18:45] CREST-MacBook-Pro-2: bomb $ rabin2 -l bomb
[Linked libraries]
libc.so.6
1 library
[18:45] CREST-MacBook-Pro-2: bomb $
```

2. Load up the binary code in radare2
```bash
[18:45] CREST-MacBook-Pro-2: bomb $ r2 bomb
syntax error: error in error handling
syntax error: error in error handling
syntax error: error in error handling
 -- THIS IS NOT A BUG
[0x00400c90]>
```

3. Cheat Sheet
```bash
// Package Manager
r2pm init
r2pm update
//Install www-m (material webui):
r2pm -i www-m
```
```bash
// General information about a file
rabin2 -I <file>
-l - dynamic libs
-i - symbols
```
```bash
// Load the binary code
r2 <binary_code>
aa - automatic analysis
afl - look at symbols and functions
s - seek to <symbol>
pdf - print disassembly of a function (e.g. pdf @ main)
V - enter visual mode, press V again to enter graph mode
hjkl - navigation
```
