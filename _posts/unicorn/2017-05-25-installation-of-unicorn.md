---
layout: blog
title:  "Installation/Configuration of Unicorn"
date:   2017-05-25 15:30:13 -0300
category: unicorn
meta: Unicorn can be installed in OSX (Sierra), Linux, and Windows
folder: unicorn
---
## Installation/Configuration of Unicorn

**Unicorn** can be installed in OSX (Sierra), Linux, and Windows. I have installed it on OSX and Linux.
I will leave some workarounds that I used to manage the unexpected hiccups during the installation in OSX and Linux.

- Unicorn official website: [http://www.unicorn-engine.org/](http://www.unicorn-engine.org/)
- Test codes: http://www.unicorn-engine.org/samples/test1.tgz
- Installation: [https://github.com/unicorn-engine/unicorn/blob/master/docs/COMPILE.md](https://github.com/unicorn-engine/unicorn/blob/master/docs/COMPILE.md)

* **OSX**  
There is an issue on testing with unicorn.
```python
[21:03] 149-161-212-7: test1 $ make
cc  test1.c -L/usr/local/Cellar/glib/2.52.0/lib -L/usr/local/opt/gettext/lib -lglib-2.0 -lintl -lpthread -lm -lunicorn -o test1
test1.c:5:10: fatal error: 'unicorn/unicorn.h' file not found
#include <unicorn/unicorn.h>
         ^
1 error generated.
make: *** [test1] Error 1
```
It requires clang of XCode. In order to get the clang, make sure that XCode is installed with the "Command Line Tools".  
As [The useful link of installation of "Command Line Tools"](http://railsapps.github.io/xcode-command-line-tools.html) mentions,
`xcode-select --install` did not work for me because it kept failing to get the
"Command Line Tools" due to the network issues. My network was just fine but it
seemed that my MBP could not get the "Command Line Tools" from the Apple App Store.
So, I just downloaded the "Command Line Tools" dmg file from [here](https://developer.apple.com/downloads/more) as the above link suggests.
Other than this, `brew install unicorn` made unicorn works just fine based on the [unicorn tutorials](http://www.unicorn-engine.org/docs/tutorial.html).
* **Linux**  
So far I did not have any issues with the [github version](https://github.com/unicorn-engine/unicorn/blob/master/docs/COMPILE-NIX.md).
`UNICORN_ARCHS="arm aarch64 x86" ./make.sh`
I lied! There was an issue on ubuntu-16.04 (cc-5.4.0) which does not compile the unicorn test codes without "-pthread" option.
So, the workaround is that we have to put the `-pthread` option in the Makefile or add it on the fly.
The test codes that I played with is in [here](http://www.unicorn-engine.org/samples/test1.tgz).
I realized that this option is not necessary in Debian-8 (cc-4.9.5). It may not be necessary for the other distros either.
Please check it out.
