---
title: "Quarkus 3.38.1 - Maintenance release"
url: "https://quarkus.io/blog/quarkus-3-38-1-released/"
date: "2026-08-05"
author: "Guillaume Smet (https://twitter.com/gsmet_)"
feed_url: "https://quarkus.io/feed"
---
Today, we released Quarkus 3.38.1, a maintenance release for our 3.38 release train. This release contains bugfixes and fixes the following CVE: CVE-2026-50559 - HTTP path-based authorization bypass via encoded semicolons, slashes, and backslashes It should be a safe upgrade for anyone already using 3.38. Update To update to Quarkus 3.38, we recommend updating to the latest version of the Quarkus CLI and run: quarkus update Note that quarkus update can update your applications from any version of Quarkus (including 2.x) to Quarkus 3.38.
