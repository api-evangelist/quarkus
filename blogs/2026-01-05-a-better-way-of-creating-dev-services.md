---
title: "A Better Way of Creating Dev Services"
url: "https://quarkus.io/blog/new-dev-services-api/"
date: "Mon, 05 Jan 2026 00:00:00 +0000"
author: "Holly Cummins (https://twitter.com/holly_cummins)"
feed_url: "https://quarkus.io/feed"
---
In Quarkus 3.25, a new API for creating Dev Services was introduced. This new model fixes a problem where all Dev Services for all tests would start in the JUnit discovery phase, potentially causing port conflicts, configuration cross-talk, and excessive resource usage. This issue was a side effect of the test classloading rewrite in Quarkus 3.22.
