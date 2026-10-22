# Cybersecurity CTF & Lab Journal

My hands-on cybersecurity learning journal: CTF challenges, lab exercises, tools, and lessons learned.

> **Portfolio note:** Writeups reflect authorized training environments only. Do not publish active competition flags or challenge solutions prohibited by platform rules.

## 📊 Challenge Dashboard

<!-- STATS_START -->
**Completed:** 1 · **In progress:** 0 · **Platforms:** 1
<!-- STATS_END -->

## 🔎 Challenge Database

Browse the challenges below. Click a challenge to read its full methodology, findings, and takeaways.

<!-- TABLE_START -->
| Challenge | Platform | Difficulty | Category | Status | Completed |
|---|---|---|---|---|---|
| [Brute It](tryhackme/brute-it/README.md) | TryHackMe | Easy | Web Exploitation | Completed | 2026-05-08 |
<!-- TABLE_END -->

## 🧰 Skills I'm Practicing

- Network enumeration and service discovery
- Linux and Windows administration and security
- Web application security
- Privilege escalation and incident detection
- Clear technical documentation

## 🗂 Repository Structure

```text
tryhackme/       # TryHackMe room writeups
hackthebox/      # Hack The Box machine writeups
picoctf/         # picoCTF challenge writeups
templates/       # Copyable writeup template
scripts/         # Database index generator
```

## ➕ Adding a Challenge

1. Copy `templates/challenge-template` into `tryhackme/`, `hackthebox/`, or `picoctf/` and rename it with a lowercase hyphenated slug.
2. Edit `metadata.json` (title, difficulty, category, status, and date) and `README.md` (your technical writeup).
3. Run `python3 scripts/update_index.py` or simply push to GitHub: the included workflow regenerates this dashboard automatically.
4. Add screenshots to the challenge's `images/` folder, and reference them relatively from its README.

**Useful convention:** Keep notes for unfinished labs with `"status": "In Progress"`, and use a date like `2026-10-22` once complete.

## 🔗 Profiles

- TryHackMe: https://tryhackme.com/p/xhatd
- Hack The Box: _add your profile link_
- LinkedIn: _add your profile link_
