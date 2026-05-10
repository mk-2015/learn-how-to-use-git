# Git Quick Reference manual

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
- Commit:  
  `git commit -m "Message here"`
- Push branch:  
  `git push -u origin main`

### Rename master to main
- Push all changes to master first:
 `git push -u origin master`
- Now do the switching:
 `git branch -M main`
 `git push -u origin main`



## Branch Management
- Rename branch to main:  
  `git branch -M main`
- List branches:  
  `git branch`
- Switch branch:  
  `git checkout branchname`

## Handling Remote Conflicts
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

## Notes
- Keep private key (`id_ed25519`) safe.  
- Only share public key (`id_ed25519.pub`).  
- Use SSH URLs for private repos.  
