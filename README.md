# first_app — how to connect to GitHub

This repository contains a simple Java project. Below are step-by-step PowerShell commands to connect this folder to GitHub (create remote, push). Run these commands in PowerShell.

1) Open PowerShell and change to the project folder:

```powershell
Set-Location "C:\Users\Veronica Monopolio\OneDrive\Documents\first_app"
```

2) (Optional) Set your Git identity for this repository:

```powershell
git config --local user.name "Your Name"
git config --local user.email "your_email@example.com"
```

3) Initialize, add files, and create the initial commit:

```powershell
git init
git add .
git commit -m "Initial commit"
git branch -M main
```

4) Create the remote repository on GitHub (choose one):

- Option A — using GitHub CLI (`gh`) (recommended):

```powershell
# If you don't have gh, install via winget
winget install --id GitHub.cli

gh auth login
gh repo create your-username/your-repo-name --public --source=. --remote=origin --push
```

- Option B — via the GitHub website:

  1. Go to https://github.com/new and create a new repository (do NOT initialize with a README since you already committed locally).
  2. Copy the repository URL (HTTPS or SSH).

5) If you used the website or want to add the remote manually, run one of the following:

```powershell
# HTTPS
git remote add origin https://github.com/your-username/your-repo-name.git
git push -u origin main

# OR SSH (after adding your SSH key to GitHub)
git remote add origin git@github.com:your-username/your-repo-name.git
git push -u origin main
```

6) (Optional) Create and add an SSH key to GitHub:

```powershell
ssh-keygen -t ed25519 -C "your_email@example.com"
Get-Content $env:USERPROFILE\.ssh\id_ed25519.pub | clip
# Then paste the copied key into GitHub → Settings → SSH and GPG keys → New SSH key
```

7) Verify the remote and pushes:

```powershell
git remote -v
git log --oneline
```

If you need, replace `your-username/your-repo-name` with your actual GitHub username and desired repository name.

If you'd like, I can also:
- produce the exact PowerShell commands with your GitHub repo name filled in (tell me the repo name), or
- walk you through adding an SSH key step-by-step.
