---
layout: blog
title:  "Running Unicorn, Capstone and Keystone on Docker"
date:   2017-05-27 21:56:10 -0400
category: unicorn
meta: Setting up Unicorn, Capstone, and Keystone on Docker would be very useful.
folder: unicorn
---
## Running Unicorn, Capstone and Keystone on Docker

[https://github.com/dikim33/unicorn.git](https://github.com/dikim33/unicorn.git)

This is how I setup Docker for Unicorn, Capstone, and Keystone.
1. Get the Dockerfile and some test files from my forked github
```bash
git clone https://github.com/dikim33/unicorn.git uck 
``` 
2. Build a docker image with the given Dockerfile
```bash
cd uck
docker build -t <image_name> .
```
3. Run the challenge file
```bash
docker run --rm -it <image_name> uck/challenge.py uck/challenge.asm
docker run --rm -it <image_name> python uck/example_capstone.py
docker run --rm -it <image_name> python uck/example_keystone.py
docker run --rm -it <image_name> python uck/example_unicorn.py
```
