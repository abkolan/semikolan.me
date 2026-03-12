---
title: "TIL: Hugo supports multiple output formats per page"
description: "The same content can be rendered as HTML, JSON, RSS, and more simultaneously."
date: 2026-03-10
---

In `hugo.toml`, setting `home = ["HTML", "RSS", "JSON"]` under `[outputs]` tells Hugo to run the home page through three separate templates. Each format can have its own template file (e.g. `index.json`).

This is how static search indexes (FlexSearch, Pagefind) are generated at build time — no server needed.
