---
title: "Quarkus 3.33.3.1 released - LTS emergency release"
url: "https://quarkus.io/blog/quarkus-3-33-3-1-released/"
date: "2026-08-05"
author: "Guillaume Smet (https://twitter.com/gsmet_)"
feed_url: "https://quarkus.io/feed"
---
Today, we released Quarkus 3.33.3.1, an emergency release for the 3.33 LTS stream. This release fixes the following CVE: CVE-2026-16308 - Quarkus REST denial of service via unbounded multipart MIME part-header accumulation It also fixes a native image regression introduced by the Netty upgrade in 3.33.3. It should be a safe upgrade for anyone already using 3.33.
