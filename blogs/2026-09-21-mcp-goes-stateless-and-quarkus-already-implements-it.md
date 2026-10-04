---
title: "MCP goes stateless, and Quarkus already implements it"
url: "https://quarkus.io/blog/mcp-stateless/"
date: "2026-09-21"
author: "Kevin Dubois (https://twitter.com/kevindubois)"
feed_url: "https://quarkus.io/feed"
---
If you’ve been running Model Context Protocol (MCP) servers, you might have bumped into the limitations of stateful sessions. Until recently, a client had to perform an initialize handshake, get a session ID, and stick to that specific server instance for the duration of the connection. For a single-instance setup, this is fine.
