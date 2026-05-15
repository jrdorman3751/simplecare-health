# Dev Environment Setup — New Machine Guide

Follow these steps in order and you'll be ready to code and push changes to simplecare.health from any machine.

---

## 1. Install Git

**Mac:**
Open Terminal and run:
```bash
git --version
```
If Git isn't installed, macOS will prompt you to install it automatically via Xcode Command Line Tools. Click Install and wait for it to finish.

**Windows:**
Download and install from: https://git-scm.com/download/win
Use all default options during installation.

Verify it worked:
```bash
git --version
# Should return something like: git version 2.x.x
```

---

## 2. Install VS Code

Download from: https://code.visualstudio.com
Install normally. On Mac, drag to Applications. On Windows, run the installer.

---

## 3. Configure Git with Your Identity
Open VS Code → Terminal → New Terminal, then run:
```bash
git config --global user.name "username"
git config --global user.email "name@email"
```

Verify:
```bash
git config --global user.name
git config --global user.email
```
Both should return your name and email.

---

## 4. Authenticate with GitHub

**Mac:**
Install GitHub CLI (easiest auth method):
```bash
# Install Homebrew first if you don't have it
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then install GitHub CLI
brew install gh

# Authenticate
gh auth login
```
Choose: GitHub.com → HTTPS → Yes (authenticate Git) → Login with a web browser → follow prompts.

**Windows:**
Download GitHub CLI from: https://cli.github.com
Install it, then open a terminal and run:
```bash
gh auth login
```
Same choices as above.

---

## 5. Clone the Repo
Navigate to where you keep projects, then:
```bash
cd ~/Documents  # or wherever you want the folder
git clone https://github.com/jrdorman3751/simplecare-health.git
cd simplecare-health
code .          # opens the project in VS Code
```

---

## 6. VS Code Extensions to Install

Open VS Code → click the Extensions icon in the left sidebar (four squares) → search and install each:

| Extension | Why |
|-----------|-----|
| **Live Server** (by Ritwick Dey) | Right-click index.html → Open with Live Server → auto-refreshes in browser on every save. Best way to preview locally. |
| **Prettier** (by Prettier) | Auto-formats HTML and CSS so code stays clean. |
| **HTML CSS Support** (by ecmel) | Autocomplete for CSS class names inside HTML files. |
| **GitLens** (by GitKraken) | See git history, who changed what, and line-by-line blame inside VS Code. Optional but handy. |

---

## 7. Verify Everything Works

1. Open `index.html` in VS Code
2. Right-click it → **Open with Live Server**
3. Browser should open at `http://127.0.0.1:5500` showing the site
4. Make a small edit (change any text), save the file — browser should refresh automatically

Then test pushing:
```bash
git add .
git commit -m "Test commit from new machine"
git push origin main
```
Go to github.com/jrdorman3751/simplecare-health and confirm the commit shows up.

---

## 8. Daily Workflow Reminder

```bash
# Before starting work — pull latest changes
git pull

# After making edits — preview with Live Server first, then push when ready
git add .
git commit -m "What you changed"
git push origin main
```

GitHub Pages redeploys automatically within ~60 seconds of each push.

---

## Key Links
- Repo: https://github.com/jrdorman3751/simplecare-health
- Live site: https://simplecare.health
- Zoho inbox: https://mail.zoho.com
- GitHub CLI docs: https://cli.github.com/manual
- VS Code docs: https://code.visualstudio.com/docs
