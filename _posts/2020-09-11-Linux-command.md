---
layout:     post
title:      Linux Command
subtitle:   for perf test
date:       2020-09-11
author:     Tina
#header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - Linux
---

# top
# ipcs -m: show shared memory
* Column "shmid": gives the id of the memory segment
* Column "nattach": gives the number of job attached to the same shared memory

# ipcrm -m /<shared memory id/>
# kill -9 /<pid/>
# pkill -9 /<process name>: 批量delete


