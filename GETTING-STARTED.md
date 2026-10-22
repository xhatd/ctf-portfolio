# Getting started

## Create the repository
1. Log into GitHub and create a **public** repository named `ctf-portfolio` (or use a name you prefer). Do not initialize it with a README.
2. Extract this ZIP, open Terminal inside the `ctf-portfolio` folder, and run:

```bash
git init
git branch -M main
git add .
git commit -m "Initial CTF portfolio"
git remote add origin https://github.com/YOUR_USERNAME/ctf-portfolio.git
git push -u origin main
```

Replace `YOUR_USERNAME` in the remote address. GitHub will prompt you to authenticate if necessary.

## Add your first challenge
1. Duplicate `templates/challenge-template/` and move that copy to `tryhackme/your-room-name/` (or the right platform folder).
2. Edit `metadata.json` and `README.md` in that copied folder.
3. Optionally add cleaned screenshots under its `images/` directory.
4. Run `python3 scripts/update_index.py` to preview your updated root README locally.
5. Commit and push. GitHub Actions can also rebuild the dashboard automatically after pushes to `main` (provided repository Actions permissions allow writing).

## Safety & public publishing
- Never commit real passwords, API keys, tokens, private IPs belonging to others, or personal data.
- Follow each platform's writeup/spoiler policy; some active challenges prohibit public solutions.
- For employer-facing notes, emphasize reasoning, troubleshooting, defense, and lessons learned.
