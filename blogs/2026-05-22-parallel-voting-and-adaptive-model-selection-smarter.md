---
title: "Parallel voting and adaptive model selection: smarter agentic AI on a budget"
url: "https://quarkus.io/blog/introducing-voting-pattern/"
date: "2026-05-22"
author: "Mario Fusco (https://twitter.com/mariofusco)"
feed_url: "https://quarkus.io/feed"
---
In a previous article we discussed why no single agentic pattern can cover all use cases, and introduced a generic Planner abstraction that allows users to define their own orchestration strategies and combine them with the ones provided by LangChain4j out-of-the-box. For instance, there we demonstrated how a goal-oriented pattern could be extended with a reflection loop to iteratively refine a piece of generated content. Among other things, that example highlighted that having an agent evaluate its own output and loop until it reaches a quality threshold is a powerful technique.
