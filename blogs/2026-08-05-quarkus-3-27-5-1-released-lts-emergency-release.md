---
title: "Quarkus 3.27.5.1 released - LTS emergency release"
url: "https://quarkus.io/blog/quarkus-3-27-5-1-released/"
date: "2026-08-05"
author: "Guillaume Smet (https://twitter.com/gsmet_)"
feed_url: "https://quarkus.io/feed"
---
Today, we released Quarkus 3.27.5.1, an emergency release for the 3.27 LTS stream. This release fixes the following CVE: CVE-2026-16308 - Quarkus REST denial of service via unbounded multipart MIME part-header accumulation It also fixes a native image regression introduced by the Netty upgrade in 3.27.5 and upgrades the PostgreSQL JDBC driver to 42.7.13. It should be a safe upgrade for anyone already using 3.27.
