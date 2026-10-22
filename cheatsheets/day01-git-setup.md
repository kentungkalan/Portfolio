# Day 01 – Git & GitHub Setup

## One-time setup (per machine)
git config --global user.name "Your Name"
git config --global user.email "id+user@users.noreply.github.com"
git config --global init.defaultBranch main
git config --global --list            # verify

## Start a repo (local first)
git init
git add .
git commit -m "Initial commit: README and Day 1 cheat sheet"
git remote add origin https://github.com/<user>/Portfolio.git
git push -u origin main               # -u: later just `git push`

## Second machine
git clone https://github.com/<user>/Portfolio.git

## Daily loop
git pull                              # FIRST thing every session
git status                            # what changed?
git add <file>   |  git add .
git commit -m "Verb-first message: Add customer schema"
git push                              # LAST thing every session

## Inspect
git log --oneline     git diff     git remote -v

## Gotchas
- Git does not track empty folders. Add a file inside them.
- Creating the GitHub repo WITH a README → first push rejected.
  Fix: git pull --rebase origin main, then push.
- Push rejected later = the other PC pushed first. git pull, then push.
- Branch named "master"? → git branch -M main
- Use your personal account and personal data only. No company code or data, ever.
- Commit messages: imperative mood, say WHAT changed ("Add", "Fix", "Refactor").