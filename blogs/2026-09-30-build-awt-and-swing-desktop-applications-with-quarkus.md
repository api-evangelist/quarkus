---
title: "Build AWT and Swing desktop applications with Quarkus Desktop"
url: "https://quarkus.io/blog/quarkus-desktop/"
date: "2026-09-30"
author: "Fouad Almalki (https://twitter.com/engineer_fouad)"
feed_url: "https://quarkus.io/feed"
---
Java has shipped AWT and Swing for decades, and many teams still build and maintain desktop applications with them. A GraalVM native executable is attractive for these applications: it starts fast, needs no JVM on the user’s machine, and ships as one executable with a few libraries. But AWT and Swing are hard to compile natively.
