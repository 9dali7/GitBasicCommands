# GIT Tutorial

## Windows Installation
```
winget install Git.MinGit GitHub.cli
```

## Ubuntu Installation
1: Add The GitHub CLI Repository
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-key C99B11DEB97541F0
```
```
sudo apt-add-repository https://cli.github.com/packages
```

2: Update Package List
```
sudo apt update
```

3: Install Git & GitHub CLI
```
sudo apt install -y git gh
```

## Git & GitHub Setup

1: Authenticate on GitHub with the gh command:
```
gh auth login
```

2: Setup The Git Credentials For One Or Multiple Accounts:
```
git config --global user.name "Your GitHub Username"
```
```
git config --global user.email "youremail@example.com"
```

3: Verify The Configurations:
```
git config --global --list
```

4: Check Authentication:
```
gh auth status
```

## Git Usage If Your Own Repo:

1: Git Init - Setup Local Git Inside The Project Folder:
```
git init
```

2: Create The Initial Branch:
```
git branch -M main
```

3: Add Remote Repo From GitHub:
```
git remote add https://github.com/user-name/repository-name.git
```

4: Add Files To Repository And Commit Changes:
```
git add file_name
```
```
git commit -m "Description of changes"
```

5: Push Changes To The Remote Repository:
```
git push -u origin main
```

## Git Usage If In Organization Or Collaboration:

1: Clone The Repo With:
```
git clone https://github.com/organization-name/repository-name.git
```

2: Create A Branch:
```
git checkout -b main
```

3: Add Files To Repository And Commit Changes:
```
git add file_name
```
```
git commit -m "Description of changes"
```

4: Push Changes To The Remote Repository:
```
git push -u origin main
```

5: Create A Pull Request Using Gh CLI:
```
gh pr create --base main --head my-feature-branch --title "Title of the PR" --body "Description of changes"
```

## Approvation Steps If Admin Of Repo:

0: If One The Same Device, Switch Accounts From Member To Admin:
```
gh auth logout
```
```
gh auth login
```
or just use:
```
gh auth login --profile <profile-name>
```

1.1: List Pull Request (admin):
```
gh pr list
```

1.2: Review Pending Pull Requests (admin):
```
gh pr list --repo organization-name/repository-name
```

2.1: Approve The Pull Request (admin):
```
gh pr review PR_NUMBER --repo organization-name/repository-name --approve
```

2.2: Don't Approve The Pull Request And Ask For Changes (admin):
```
gh pr review PR_NUMBER --repo organization-name/repository-name --request-changes --body "Please make the following changes: [Describe the changes you want]."
```

3: Merge The Pull Request (admin):
```
gh pr merge PR_NUMBER --repo organization-name/repository-name --merge
```
