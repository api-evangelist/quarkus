---
title: "Faster Startup on IBM Semeru with OpenJ9 Shared Classes Cache"
url: "https://quarkus.io/blog/semeru-scc/"
date: "2026-05-06"
author: "Georgios Andrianakis (https://twitter.com/geoand86)"
feed_url: "https://quarkus.io/feed"
---
Slow startup times have long been a challenge for Java applications. Project Leyden addressed this for JVMs like Temurin 25+, which are based on HotSpot, but what about users of JVMs based on IBM OpenJ9 like Semeru? In our previous post, we described how we integrated Project Leyden into Quarkus, bringing JVM startup way down. But not everyone runs HotSpot-based JVMs. Many teams, especially in enterprise environments, run IBM Semeru Runtimes, IBM’s production Java runtime built on the Eclipse OpenJ9 JVM. These teams deserve the similar startup improvements, with the same ease of use.
