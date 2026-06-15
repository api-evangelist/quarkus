---
title: "Why isn't Quarkus 2x faster than Spring on my machine?"
url: "https://quarkus.io/blog/hidden-cost-rootless-container-networking/"
date: "2026-06-08"
author: "Francesco Nigro"
feed_url: "https://quarkus.io/feed"
---
A community member ran our Quarkus vs Spring CRUD benchmark on their bare-metal Fedora workstation and asked: Why do I see only 1.19x instead of 2x? Our perf-lab shows Quarkus at 2.08x Spring’s throughput, but locally the gap nearly disappears. This post walks through the investigation that found the culprit.
