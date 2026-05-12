# Git Quick Reference manual

## Resources
[Git CheatSheet](https://education.github.com/git-cheat-sheet-education.pdf)

## Setup
- Initialize repo:  
  `git init`
- Add remote (SSH):  
  `git remote add origin git@github.com:user/reposotry.git`
- Verify remotes:  
  `git remote -v`

## Authentication
- Generate SSH key:  
  `ssh-keygen -t ed25519 -C "your_email@example.com"`
- Add to agent:  
  `eval "$(ssh-agent -s)"`  
  `ssh-add ~/.ssh/id_ed25519`
- Copy public key to GitHub:  
  `cat ~/.ssh/id_ed25519.pub`

## Basic Workflow
- Stage all changes:  
  `git add .` 
  or `git rm <file>` to remvove file or `<dir>/`
  or `git mv [existing-path] [new-path]` to move file
- Commit:  
  `git commit -m "Message here"`
- Push branch:  
  `git push -u origin main`

## Rename master to main
- Push all changes to master first:
 `git push -u origin master`
- Now do the switching:
 `git branch -M main`
 `git push -u origin main`

## Clone
- Clone a repo:
  `git clone https://www.github.com/<user>/<repo>.git`
- or to do a shallow clone:
  `git clone --depth  https://www.github.com/<user>/<repo>.git`
- Add Submodule: 
  `git submodule add <url> <path>`
- Clean Submodule Cache: 
  `git rm --cached <path>`

## Branch Management
- Rename branch to main:  
  `git branch -M main`
- List branches:  
  `git branch`
- Switch branch (Create New Branch):  
  `git checkout -b branchname`
- Switch branch
  `git switch branch`
- Merge branch into current one:
  `git merge mybranch`
- Create new branch at commit:
  `git branch [branch-name]`

## Handling Remote ConflicCombines ts
- If remote has commits you don’t:  
  `git pull origin main --allow-unrelated-histories`
- If you want to overwrite remote:  
  `git push -u origin main --force`

## Submodules
- Add submodule:  
  `git submodule add <url> path/to/submodule`
- Remove accidental repo folder:  
  `git rm --cached path/to/folder`

## Useful Commands
- Show status:  
  `git status`
- Show log:  
  `git log --oneline`
- Undo staged file:  
  `git reset HEAD file`
- Undo last commit (keep changes):  
  `git reset --soft HEAD~1`

## .gitgnore
- use gitgnore to remove files to keep out of add, commit and Push
* example:
```gitgnore
*logs*/
.env
*.apikey*
*.env
```

## Notes
- Keep private key (`id_ed25519`) safe.  
- Only share public key (`id_ed25519.pub`).  
- Use SSH URLs for private repos.  