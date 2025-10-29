# 📡 Nmap Cheatsheet

## Basic Scans
- `nmap -sC -sV <target>` → default scripts & version
- `nmap -A <target>` → aggressive scan
- `nmap -p- <target>` → all ports

## Save Results
- `nmap -oN scan.txt <target>` → normal output
- `nmap -oX scan.xml <target>` → XML output

## Common Flags
- `-Pn` → skip host discovery
- `-T4` → faster timing
- `-sU` → UDP scan
