---
title: "TIL: git worktrees let you check out multiple branches at once"
description: "You don't have to stash or switch branches to work on two things in parallel."
date: 2026-02-20
---

`git worktree add ../my-feature my-feature-branch` creates a second working directory linked to the same repo. Both directories share the same `.git` folder, so you can have one branch building while you edit another.

Useful when you need to reference a different branch without losing your current working state.
