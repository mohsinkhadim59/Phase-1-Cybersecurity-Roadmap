<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [title: Git Configuration
tags: [git, config]](#title-git-configuration%0Atags-git-config)
- [📁 Repository‑Specific `.git/config`](#-repository%E2%80%91specific%C2%A0gitconfig)
- [🐙 GitHub CLI Configuration](#-github-cli-configuration)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---
title: Git Configuration
tags: [git, config]
---

```ini
[user]
    name = Your Name
    email = you@example.com
    signingkey = <gpg-key-id>   # Optional: auto‑sign commits

[core]
    editor = vim
    autocrlf = input          # For cross‑OS line endings
    safecrlf = true

[alias]
    co  = checkout
    br  = branch
    ci  = commit
    st  = status
    lg  = log --oneline --graph --decorate

[push]
    default = simple          # `git push` requires specifying branch

[diff]
    tool = vimdiff

[merge]
    tool = vimdiff
```

> **Save** to `~/.gitconfig` (Linux/macOS) or `%USERPROFILE%\.gitconfig` (Windows).  
> **Reload**: `git config --global --edit` or simply restart your terminal.

## 📁 Repository‑Specific `.git/config`

```ini
[core]
    editor = code --wait
```

> Place this in the repo’s `.git/config`.

## 🐙 GitHub CLI Configuration

```bash
# Log in (will open browser)
gh auth login

# Verify current auth
gh auth status

# Set default GitHub host (useful for self‑hosted instances)
gh config set host github.com
```