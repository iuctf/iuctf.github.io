---
layout: blog
title:  "More tricks on radare2"
date:   2017-06-29 16:42:20 -0400
category: radare2
meta: More tricks on Radare2 to create our own cheat sheet.
folder: radare2
---
## More tricks on Radare2 (Cheat Sheet)

* Cheat Sheet that we found on the web:
[https://github.com/pwntester/cheatsheets/blob/master/radare2.md](https://github.com/pwntester/cheatsheets/blob/master/radare2.md)

We try to keep all the useful tricks of Radare2 here.

1. Why do we put "@" in front of a register when we inspect it via "pxq", "ps",
"pdf" and so on?
```
It is because the print commands starting with the letter 'p' reads all the
memory addresses starting from the beginning (0x0) of VM address.
The p? commands without using @ will print out way more than a user expects
in the radare2 screen. That's why radare2 gives a warning of this.
The @ sign in front of a register tells the p? commands to read from the
address where the register is pointing to for now.
```

1. What are local_4h, local_8h, ...?
```bash
They are representing the local variables pointing the address
4/8/... bytes less than the "rbp" register
local_4h == rbp-4
local_12h == rbp-0x12 or rbp-18
```
