---
title: "A Go CEL Policy Engine in Java, with Quarkus Chicory"
url: "https://quarkus.io/blog/k8s-style-CEL-with-quarkus-chicory/"
date: "Thu, 19 Feb 2026 00:00:00 +0000"
author: "Fabio Burzigotti"
feed_url: "https://quarkus.io/feed"
---
A few days ago, we released the first version of Quarkus Chicory , an extension that brings the power of the Chicory WebAssembly runtime to Quarkus applications. While iterating on development, we felt the need to implement an integration test based on a real world use case. After some research and experiments on popular scenarios we finally landed on a tasty one :-) A Kubernetes-style CEL Policy Engine CEL allows expression based policy validation of Kubernetes resources, and this requirement is implemented by operators…​ which are generally written in Go :-) But Quarkus Java based…
