---
title: git-push-warning
categories: [git]
tags: [git, push, warning]
date: 2015-01-24 16:04:36
---

# warning: push.default is unset;

```
warning: push.default is unset; its implicit value is changing in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the current behavior after the default changes, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

In Git 2.0, Git will default to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.
```

# 解决

-   默认只推送当前分支

        git config --global push.default simple
