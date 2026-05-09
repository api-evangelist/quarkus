---
title: "Introducing Quarkus Agent MCP: teaching AI agents to speak Quarkus"
url: "https://quarkus.io/blog/introducing-agent-mcp/"
date: "2026-05-07"
author: "Phillip Kruger (https://twitter.com/phillipkruger)"
feed_url: "https://quarkus.io/feed"
---
AI coding agents like Claude Code, GitHub Copilot, Cursor, Windsurf, and JetBrains AI are already capable of generating code, fixing bugs, and refactoring entire modules. But they become much more effective when they have context about the framework you are using: that Quarkus dev mode hot-reloads on the next request rather than on file save, that Panache entities need @Transactional for writes, that REST clients should be injected via CDI rather than instantiated manually. Quarkus Agent MCP gives agents exactly that context.
