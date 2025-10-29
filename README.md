# Introduction to Phase-1 

**Author:** Muhammad Mohsin Khadim

## What Phase-1 teaches
Phase-1 is a focused 30-day hands-on pack that trains you in the fundamentals of offensive security:

- Linux command line & basic **Bash** scripting (files, permissions, pipes).  
- Network discovery & enumeration (nmap, netcat basics).  
- Basic web vulnerabilities and testing (SQLi, XSS, auth bypass).  
- Lab workflow: enumerate → exploit → privilege escalation → write-up.  
- How to create compact cheatsheets and reproducible lab write-ups.

## Minimum requirements
- **A Linux environment** (native Linux, Linux VM, or WSL2).  
- Enough resources to run at least one VM: **~8GB RAM recommended** if you plan to run target VMs locally.  
- Basic command-line familiarity (comfortable with terminal, editing files).

## Essential software for this repo (open & use)
- **Obsidian** — primary viewer for notes/cheatsheets (this repo mirrors an Obsidian vault).  
- **Git** — to version the repo (optional if you only browse).  
- **VirtualBox / VMware** — to run target VMs (VulnHub/Kioptrix) if you run labs locally.  
- **A Linux distro for attacker tasks** — Kali recommended but any distro works.  
- **Terminal / SSH client** — native terminal or Windows Terminal + WSL2.  
- Web browser (Firefox/Chrome) for PortSwigger/online labs.

## Obsidian — how to open & quick tips
1. Install Obsidian and choose **Open folder as vault** → point to this repo folder.  
2. Key folders you’ll see in the vault: `docs/`, `cheatsheets/`, `labs/`, `scripts/`.  
3. Recommended minimal plugins (optional):  
   - **Backlinks / Graph** (built-in) for navigation.  
   - **Quick switcher / search** for fast lookup.  
4. Keep `.obsidian/` and any heavy caches out of Git (add to `.gitignore`).

## Notes on safety & sharing
- Practice only on machines you own or have explicit permission to test.  
- Sanitize flags, credentials, and secrets before committing any lab outputs to the repo.

---
