---
title: "To Cache or Not to Cache Virtual Threads"
url: "https://quarkus.io/blog/to-cache-or-not-to-cache-virtual-threads/"
date: "2026-07-28"
author: "Francesco Nigro"
feed_url: "https://quarkus.io/feed"
---
The official guidance on virtual threads is clear: Virtual threads are cheap and plentiful, and thus should never be pooled: A new virtual thread should be created for every application task. — Ron Pressler & Alan Bateman, JEP 444: Virtual Threads Creating a virtual thread is cheap — have millions, and don’t pool them! — Ron Pressler, State of Loom As part of our work on improving Quarkus performance with virtual threads and investigating Loom’s scheduling behavior , we decided to test this advice with data.
