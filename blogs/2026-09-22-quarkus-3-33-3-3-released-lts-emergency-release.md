---
title: "Quarkus 3.33.3.3 released - LTS emergency release"
url: "https://quarkus.io/blog/quarkus-3-33-3-3-released/"
date: "2026-09-22"
author: "Jan Martiška (https://twitter.com/janmartiska)"
feed_url: "https://quarkus.io/feed"
---
Today, we released Quarkus 3.33.3.3, an emergency release for the 3.33 LTS stream. This release fixes the following CVEs: CVE-2026-77874 - Hibernate ORM: SQL Injection via unescaped JSON path segment allows data exfiltration and authorization bypass CVE-2026-19611 - WildFly Elytron: Password keyspace reduction via NFKC fullwidth folding CVE-2026-81829 - SmallRye JWT: Unauthenticated same-origin SSRF via unsanitized JWT kid header in AwsAlbKeyResolver CVE-2026-87742 - Quarkus WebSockets Next: Denial of Service (OOM) via unbounded message buffering CVE-2026-87743 - Quarkus Vert.x HTTP: Authoriza
