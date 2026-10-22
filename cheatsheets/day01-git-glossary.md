# Day 01 – Git Glossary (what / when / where)

## The big picture: 4 places your work lives
```
 YOUR PC ─────────────────────────────────────────────┐      GITHUB
 Working tree  ──git add──▶  Staging area  ──git commit──▶  Local repo  ──git push──▶  Remote (origin)
 (files you edit)            (next snapshot)              (.git folder)  ◀──git pull──  (github.com)
 └────────────────────────────────────────────────────┘
```

## Places
| Term | What it is | Where it lives |
|---|---|---|
| **Working tree** | The normal files you see and edit | Your Portfolio folder |
| **Staging area** (index) | A list of changes you've picked for the next commit | Inside `.git` (invisible) |
| **Local repository** | Full history of every commit | The hidden `.git` folder. Delete it and the history is gone |
| **Remote** | A copy of the repo on another computer/server | GitHub |
| **origin** | Nickname for your main remote (set by `git remote add` / `git clone`) | `git remote -v` shows its URL |

## Things
| Term | What it is | When you see it |
|---|---|---|
| **Repository (repo)** | A project folder tracked by Git | `git init` / `git clone` creates one |
| **Commit** | A saved snapshot of staged files + message + author + time | After every meaningful change |
| **Hash** (`63c4c77`) | Unique ID of a commit | `git log --oneline` |
| **Branch** (`main`) | A named line of commits; a pointer to the latest one | `git status` → "On branch main" |
| **HEAD** | "Where you are now", usually points to your current branch | `HEAD -> main` in `git log` |
| **origin/main** | Your PC's last-known position of GitHub's main | Behind `main` = you haven't pushed |

## File states (what `git status` tells you)
| State | Meaning | Colour | Next step |
|---|---|---|---|
| **Untracked** | New file Git has never seen | red | `git add` |
| **Modified** | Tracked file changed since last commit | red | `git add` |
| **Staged** | Picked for the next commit | green | `git commit` |
| **Committed** | Safely in history ("working tree clean") | — | `git push` |

## Actions
| Command | What it does | When |
|---|---|---|
| `git config --global` | Sets your name/email/editor for every repo on this PC | Once per machine |
| `git init` | Turns a folder into a repo (creates `.git`) | Once, starting a new project |
| `git clone <url>` | Downloads a full repo + sets up origin | Once per extra machine |
| `git status` | Shows file states | Constantly — before add, before commit |
| `git add` | Moves changes to the staging area | Before every commit |
| `git commit -m` | Saves the staged snapshot locally | After a logical chunk of work |
| `git push` | Uploads your commits to GitHub | End of every session |
| `git pull` | Downloads + combines GitHub's commits into yours | **Start** of every session |
| `git diff` | Shows unstaged line-by-line changes | Before `git add`, to review |
| `git log --oneline` | Lists commit history | To check sync with origin |

## Words you'll see in output
| Term | Meaning |
|---|---|
| **Fast-forward** | Pull just moved your branch forward; nothing to combine. The good case |
| **Merge** | Git combined two lines of commits (may open `MERGE_MSG` in VS Code — close it to accept) |
| **Merge conflict** | Both sides changed the same lines; you must choose. Prevent: pull first |
| **Rejected push** | GitHub has commits you don't. Fix: `git pull`, then `git push` |
| **pathspec did not match** | Wrong file path. Use **Tab** to autocomplete |
| **`<placeholder>`** | In docs: replace it, including the `< >` |

## Setup terms
| Term | Meaning |
|---|---|
| **PATH** | Windows' list of folders to search for commands. Why `git`/`code` work in any terminal. Needs a new terminal after install |
| **Git Credential Manager** | Stores your GitHub login so push doesn't ask every time |
| **noreply email** | GitHub-provided address that links commits to you without exposing your real email |
| **CRLF / LF** | Windows vs Unix line endings. Git converts automatically with your install setting |
| **.gitignore** | File listing what Git should never track (secrets, data dumps, temp files) |

## Learn more
- Pro Git 1.3 – the three states: https://git-scm.com/book/en/v2/Getting-Started-What-is-Git%3F
- Pro Git 2.2 – recording changes: https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository
- Pro Git 2.5 – working with remotes: https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes
- GitHub glossary: https://docs.github.com/en/get-started/learning-about-github/github-glossary
- Video (2 min): Git Explained in 100 Seconds – https://www.youtube.com/watch?v=hwP7WQkmECE
