---
layout: blog
title:  "Introduction to Unicorn"
date:   2017-05-23 19:49:37 -0300
category: unicorn
meta: Unicorn is an open source CPU emulator based on QEMU
folder: unicorn
---
## Introduction to Unicorn

**Unicorn** is an open source CPU emulator based on QEMU.

Nice features that I would like to share (*quoted from [the unicorn page](http://www.unicorn-engine.org/docs/beyond_qemu.html)*):
* Framework: QEMU is a set of emulators, but not a framework. Therefore, you
  cannot build your own tools on top of QEMU, while this is the main purpose of
  Unicorn.

* Flexible: QEMU cannot emulate a chunk of raw binary code without any context:
  it requires either a proper executable binary (for example, a file in ELF
  format), or a whole system image with a full OS inside. Meanwhile, Unicorn
  just focuses on CPU operations, and can emulate raw code without context 

* Instrumentation: QEMU does not support dynamic instrumentation, but with
  Unicorn you can register customized handlers for various kind of events from
  CPU execution to memory access. This feature gives tool programmers all the
  power they need to monitor and analyze the code under emulation.

* Thread-safe: QEMU cannot handle more than one CPU at the same time. In
  contrast, Unicorn is designed and implemented as a framework so that one
  program can emulate multiple code of different kinds of CPU in a moment.

* Bindings: QEMU does not have binding itself. But as a framework, Unicorn
  supports multiple bindings on top of the core written in C. This makes it
  easy to be adopted by developers. A rich list of efficient bindings - 4
  languages have been supported in version 0.9 - lowers the barrier for every
  programmer.

* Lightweight: Unicorn is much more lightweight than QEMU because we stripped
  all the subsystems that do not involve in CPU emulation. As a result, Unicorn
  is less than 10 times smaller in size and also in memory consumption.

* Safety: QEMU has a bad track of security record with a lot of vulnerabilities
  that can be exploited to break out of the guest. Its history says that all of
  these bugs are from subsystems such as devices, BIOS, firmware etc, but none
  of them comes from CPU emulator component. Therefore, in principle Unicorn is
  much more secure because it has way smaller attack surface.
