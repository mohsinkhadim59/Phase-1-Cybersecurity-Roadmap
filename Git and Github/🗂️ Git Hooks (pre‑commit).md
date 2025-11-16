<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [title: Further Reading – Git & GitHub
tags: [git, github, resources]](#title-further-reading--git--github%0Atags-git-github-resources)
- [📚 Further Reading](#-further-reading)
- [🗂️ Git Hooks (pre‑commit)](#-git-hooks-pre%E2%80%91commit)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---
title: Further Reading – Git & GitHub
tags: [git, github, resources]
---

## 📚 Further Reading

| Resource                     | Link                                                          | Description                                        |
|------------------------------|---------------------------------------------------------------|-----------------------------------------------------|
| **Pro Git book (free)**     | https://git-scm.com/book/en/v2                               | Comprehensive, in‑depth guide from the git‑core team. |
| **GitHub Docs**             | https://docs.github.com/en                                   | Official GitHub documentation – API reference, best practices, etc. |
| **GitHub CLI Cheat Sheet**  | https://github.com/cli/cli/blob/trunk/docs/cheatsheet.md     | Quick reference for the `gh` command‑line tool.     |

> **Tip** – Feel free to add your own bookmarks or extend the table with tutorials you find useful.  
> You can transclude this note into a “Git Knowledge Base” or reference it from your project README with `![[Further Reading – Git & GitHub]]`.

---

## 🗂️ Git Hooks (pre‑commit)

Create a `pre-commit` hook in your repository’s `.git/hooks/` directory:

```bash
#!/bin/sh
# Example: run lint before commit
./scripts/lint.sh
if [ $? -ne 0 ]; then
  echo "Lint failed – abort commit"
  exit 1
fi
```

Make it executable:

```bash
chmod +x .git/hooks/pre-commit
```

> _Keep this file handy for a quick setup or copy it into new projects._