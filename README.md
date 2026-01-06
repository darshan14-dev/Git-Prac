# Git Complete Guide & Cheat Sheet

This README contains **Git setup, configuration, repository management, branching, collaboration, history inspection, tagging, and production-level commands** all in one place.

---

## 1️⃣ Git Setup & Configuration

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Set global username | `git config --global user.name "Your Name"` | Sets name for commits |
| Set global email | `git config --global user.email "you@example.com"` | Email used for commits |
| Set default editor | `git config --global core.editor "code --wait"` | Opens VSCode for commit messages |
| Set default merge tool | `git config --global merge.tool vimdiff` | Use vimdiff for merging |
| View current config | `git config --list` | Lists all configuration |
| Enable colored output | `git config --global color.ui auto` | Makes Git output easier to read |

---

## 2️⃣ Repository Management

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Initialize new repo | `git init` | Starts a new Git repository |
| Clone repository | `git clone <url>` | `git clone https://github.com/user/repo.git` |
| Clone specific branch | `git clone -b branch-name <url>` | `git clone -b dev https://github.com/user/repo.git` |
| Check status | `git status` | Shows staged/unstaged changes |
| List tracked files | `git ls-files -s` | Shows files in index |

---

## 3️⃣ Staging & Committing

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Stage a file | `git add <file>` | `git add index.html` |
| Stage all files | `git add .` | Stage everything |
| Commit changes | `git commit -m "<message>"` | `git commit -m "Implement login"` |
| Amend previous commit | `git commit --amend -m "<message>"` | Update commit message or add changes |
| Skip pre-commit hooks | `git commit --no-verify -m "<message>"` | Use with caution |
| Stage part of file | `git add -p <file>` | Stage selected chunks |

---

## 4️⃣ Branching & Merging

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| List branches | `git branch` | Shows local branches |
| Create branch | `git branch <name>` | `git branch feature/login` |
| Switch branch | `git checkout <branch>` | `git checkout main` |
| Create & switch | `git switch -c <branch>` | `git switch -c feature/login` |
| Merge branch | `git merge <branch>` | `git merge feature/login` |
| Merge no fast-forward | `git merge --no-ff <branch>` | Keeps merge history |
| Delete local branch | `git branch -d <branch>` | `git branch -d feature/login` |
| Delete remote branch | `git push origin --delete <branch>` | `git push origin --delete feature/login` |

---

## 5️⃣ Remote Repositories & Collaboration

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Show remotes | `git remote -v` | List remote repositories |
| Add remote | `git remote add origin <url>` | `git remote add origin https://github.com/user/repo.git` |
| Fetch updates | `git fetch origin` | Fetch changes without merging |
| Pull with merge | `git pull origin main` | Merge remote changes |
| Pull with rebase | `git pull --rebase origin main` | Preferred in teams |
| Push branch | `git push origin <branch>` | `git push origin main` |
| Force push | `git push origin <branch> --force` | Use carefully |
| Track remote branch | `git checkout --track origin/<branch>` | `git checkout --track origin/feature/login` |

---

## 6️⃣ Stashing, Cleaning & Undoing

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Save changes | `git stash` | Stash uncommitted changes |
| Apply stash | `git stash apply` | Apply without removing |
| Apply & remove stash | `git stash pop` | Apply and delete stash |
| List stashes | `git stash list` | Shows all stashes |
| Drop a stash | `git stash drop stash@{0}` | Delete specific stash |
| Clear all stashes | `git stash clear` | Remove all stashes |
| Discard file changes | `git checkout -- <file>` | Discard changes in working dir |
| Unstage file | `git reset HEAD <file>` | Remove from staging |
| Soft reset | `git reset --soft HEAD~1` | Keep changes staged |
| Hard reset | `git reset --hard HEAD~1` | Discard changes |
| Clean untracked files | `git clean -f` | Remove untracked files |
| Clean files & dirs | `git clean -fd` | Remove untracked dirs too |

---

## 7️⃣ Inspecting History & Logs

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Full commit history | `git log` | Shows all commits |
| One-line summary | `git log --oneline` | Condensed view |
| Graphical history | `git log --graph --oneline --all` | Visualize branch structure |
| Show commit details | `git show <hash>` | Details of specific commit |
| Show unstaged changes | `git diff` | Differences in working dir |
| Show staged changes | `git diff --staged` | Differences staged for commit |
| Compare branches | `git diff branch1..branch2` | Diff between branches |

---

## 8️⃣ Tagging & Releases

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Create annotated tag | `git tag -a v1.0.0 -m "Release v1.0.0"` | For production releases |
| Create lightweight tag | `git tag v1.0.0-light` | Simple tag without annotation |
| Push tag | `git push origin v1.0.0` | Push specific tag |
| Push all tags | `git push --tags` | Push all tags to remote |
| Delete local tag | `git tag -d v1.0.0` | Remove tag locally |
| Delete remote tag | `git push origin --delete tag v1.0.0` | Remove tag remotely |

---

## 9️⃣ Production-Level Commands & Best Practices

| Purpose | Command | Example / Notes |
|---------|---------|----------------|
| Rebase onto main | `git rebase main` | Keeps history clean |
| Interactive rebase | `git rebase -i HEAD~5` | Reorder/squash commits |
| Squash commits | `git rebase -i main` | Combine commits for release |
| Cherry-pick commit | `git cherry-pick <hash>` | Apply a single commit |
| Show remote branches | `git branch -r` | List tracked branches |
| Verify repo integrity | `git fsck` | Checks repo health |
| Check ignored files | `git check-ignore -v *` | Debug ignore rules |
| Merge conflicts tool | `git mergetool` | Resolve conflicts visually |
| Pull & rebase | `git pull --rebase origin main` | Avoid merge commits |
| Force push after rebase | `git push origin <branch> --force-with-lease` | Safe force push |

---

✅ **Summary of Best Practices**

1. Always use **feature branches**; keep `main/master` stable.
2. Prefer **rebase** over merge for cleaner history.
3. Use **git stash** for temporary work in progress.
4. **Visualize history** with `git log --oneline --graph --all`.
5. Tag releases with **annotated tags** for production.
6. Use **--force-with-lease** when force-pushing.
7. **Clean up old branches** regularly.

---

This README contains **everything a developer needs for day-to-day Git usage**, from setup to production-level workflows.
