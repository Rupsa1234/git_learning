### Section 1: Foundation & Local Repository
## Task 1.1: Environment Setup & Configuration
1. Setup Git Bash/Terminal
2. Repository Creation

# Usage Levels of Configuration
Scope	    Command	Affects	Stored In
Local	    git config --local (default)	Only in the current repo	
Global	    git config --global          	All repos for this user	
System-wide	git config --system     	    All users on the system	

![alt text](screenshots-git/image.png)

## Task 1.2: Basic File Operations
1. Create and commit files:

![alt text](screenshots-git/image-1.png)

![alt text](screenshots-git/image-2.png)

2. Practice staging
![alt text](screenshots-git/image-3.png)

![alt text](screenshots-git/image-4.png)

![alt text](screenshots-git/image-5.png)

- git diff - This command shows the difference between the working directory and the staging area.

# Command Shows
git diff	Working directory ↔ Staging area
git diff --staged	Staging area ↔ Last commit
git diff HEAD	Working directory ↔ Last commit
git diff branch1..branch2	Differences between branches

![alt text](screenshots-git/image-6.png)

## Task 1.3: History and Undoing Changes

1. Explore Git history:

- git log --oneline
Shows a compact log with each commit in one line:

![alt text](screenshots-git/image-7.png)

- git log --graph
Displays the branch and merge history as a graph:

![alt text](screenshots-git/image-8.png)

- git log --decorate
Adds branch/tag names to commits:

![alt text](screenshots-git/image-9.png)


2. Practice undoing changes:
- Make a "bad" commit (add wrong content)
![alt text](screenshots-git/image-12.png)

- Practice git revert to undo it
git revert <commit-hash>
![alt text](screenshots-git/image-13.png)

- Make another change and practice git reset
![alt text](screenshots-git/image-14.png)

git reset --soft <hash>     : Uncommit, keep changes staged

![alt text](screenshots-git/image-15.png)

git reset --mixed <hash>	: Uncommit, changes unstaged

![alt text](screenshots-git/image-16.png)

git reset --hard <hash>     : Uncommit and delete changes completely

![alt text](screenshots-git/image-12.png)



- Document the differences between revert and reset
🔁 git revert                                              vs                                        git reset

Purpose	Undo a specific commit by creating a new commit	                   Move the current branch to a previous commit (and maybe remove changes)
History-safe?	✅ Yes (safe for shared/public repos)	                 ❌ No (can rewrite history — unsafe for shared branches)
Creates a new commit? ✅ Yes      	                                     ❌ No (unless used with --soft, then commit can follow)
Data loss risk?	❌ Low	                                                 ⚠️ High (with --hard, deletes changes permanently)
Common use :Undo changes without affecting commit history	               Rewind history or unstage/remove local commits
Best for :	Public/shared repositories	                                   Private/local branches or fixing recent mistakes


## Task 1.4: File Management
1. Gitignore: .gitignore is a plain text file that tells Git which files or folders to ignore — meaning:

They won’t be tracked
They won’t be committed
They won’t appear in git status

![alt text](screenshots-git/image-10.png)

2. File removal:

![alt text](screenshots-git/image-11.png)

### Section 2: Branching & Merging Mastery
## Task 2.1: Branch Creation & Management
1. Create feature branches:

![alt text](screenshots-git/image-17.png)

2. Switch between branches and add different features
   Make at least 2 commits per branch

![alt text](screenshots-git/image-18.png)

![alt text](screenshots-git/image-19.png)

  Practice git branch -a to see all branches

 ![alt text](screenshots-git/image-20.png)

## Task 2.2: Branching
1. Create branches from specific commits:
- Now create your new branch hotfix/urgent-fix from  that commit:
- Switch to the New Branch:
![alt text](screenshots-git/image-21.png)

![alt text](screenshots-git/image-22.png)

2. Branch naming conventions:
- Rename poorly named branches

![alt text](screenshots-git/image-25.png)

- Practice deleting branches (both local and remote)

Steps:
- create a new branch and push to remote:
![alt text](screenshots-git/image-26.png)

- Switch Back to Another Branch(You cannot delete a branch while you're on it.)

# Delete the Branch Locally
  git branch -d test/delete-demo

![alt text](screenshots-git/image-27.png)

# Delete the Branch Remotely
  git push origin --delete test/delete-demo

![alt text](screenshots-git/image-28.png)


## Task 2.3: Merging Strategies
1. Merges:
Merge feature/navigation into main

![alt text](screenshots-git/image-23.png)

Observe the linear history

![alt text](screenshots-git/image-24.png)


2. Three-way merges:
- Create conflicting changes in different branches
- Practice resolving merge conflicts manually
- Complete the merge with proper commit message

![alt text](screenshots-git/image-30.png)

![alt text](screenshots-git/image-29.png)

![alt text](screenshots-git/image-31.png)

## Task 2.4: Merge Conflict Resolution
1. Intentional conflicts:
- Create two branches that modify the same lines
- Practice conflict resolution using:
- Command line tools

![alt text](screenshots-git/image-32.png)

![alt text](screenshots-git/image-33.png)

![alt text](screenshots-git/image-34.png)

- VS Code merge editor

![alt text](screenshots-git/image-30.png)

![alt text](screenshots-git/image-29.png)

![alt text](screenshots-git/image-31.png)

## Task 2.5: Challenge
![Create a "Git Branching Strategy" document:](screenshots-git/git_branching_strategy.md)

### Section 3: Remote Repositories & GitHub Integration
## Task 3.1: GitHub Repository Setup

1. Create remote repository:
- Create git_learning repository on GitHub

![Link your local repository to remote](screenshots-git/image-36.png)

![Push all branches to remote](screenshots-git/image-37.png)

![github repo](screenshots-git/image-38.png)

2. Remote operations:
Practice git remote -v
Add multiple remotes (if you have access to another Git service)
![git remote add backup https://github.com/Rupsa1234/backup_git-learning.git](screenshots-git/image-39.png)

![push to backup](screenshots-git/image-40.png)

Term	                          Meaning
origin	-   The default remote (your repo on GitHub, usually where you push)
upstream-	The original project (if you forked someone else's repo)

## Task 3.2: Cloning & Forking
1. Clone operations:

![Clone your repository to a different location](screenshots-git/image-41.png)

Practice working with both local copies
- pushing and pulling between two local clones of the same remote repo.

![In the first folder:](screenshots-git/image-42.png)

![In the second folder:](screenshots-git/image-43.png)

Understand how remote tracking works

![Check tracking branches:](screenshots-git/image-44.png)

![Check remote config:](screenshots-git/image-45.png)

![Show tracking details:](screenshots-git/image-46.png)

2. Fork a public repository:

Fork an interesting open-source project

![Forking](screenshots-git/image-47.png)

Clone your fork locally

![make small improvements](screenshots-git/image-48.png)

push to your fork

![push to repo](screenshots-git/image-49.png)

![Sign-Language-Recognition index.html](screenshots-git/image-50.png)

## Task 3.3: Collaboration Simulation
1. Multi-device workflow:

- Work from your cloned repository

![cloned to different folder](screenshots-git/image-51.png)

- Make changes and push

![change in original repo (~/git_learning/Sign-Language-Recognition):](screenshots-git/image-52.png)

- Pull changes from the original repository

![in Sign-Language-Recognition-copy](screenshots-git/image-53.png)

2. Fetch vs Pull:

- Practice git fetch operations

- Compare local and remote branches

![From one clone, make a change and push:](screenshots-git/image-54.png)

![From second clone fetch](screenshots-git/image-55.png)

![merge and pull from second clone](screenshots-git/image-56.png) Or just: git pull origin master

You want to preview changes without merging	-git fetch
You're collaborating and need latest code -	git pull
You want more control over merge conflicts -git fetch + manual merge

Task 3.4: Pull Request Workflow
1. Create pull requests:

Create feature branches

![new branch](screenshots-git/image-57.png)

Push to GitHub

![push](screenshots-git/image-58.png)

Create pull requests with detailed descriptions

![description](screenshots-git/image-59.png)

Practice self-review and merge

![review](screenshots-git/image-60.png)

2. Pull Request Etiquette:
Best Practice	
✅ Use clear PR title & summary	- Descriptive like "Fix login bug"
✅ Add reviewers/assignees	- Right-side GitHub panel
✅ Keep PRs small & focused	One purpose per PR
✅ Add screenshots if UI changes	Upload in description

## Task 3.5: Challenge

Set up a "fake team collaboration":
Create a second GitHub account or use a friend's
Practice the full PR workflow with reviews
Document the collaboration process

![alt text](screenshots-git/image-61.png)

## Task 4.1: Git Rebase
1. Interactive rebase:
Create a feature branch with multiple commits
Use git rebase -i to:
- Squash commits
- Reword commit messages
- Reorder commits
- Drop unnecessary commits

![commits](screenshots-git/image-62.png)

![rebase](screenshots-git/image-63.png)

Action	What it Does
pick	Keep commit as is
reword	Edit the commit message
squash	Combine commit with previous one
drop	Remove the commit

![actions](screenshots-git/image-64.png)

2. Rebase vs Merge:
Create two identical feature branches
Merge one and rebase the other
Compare the resulting history

![merge](screenshots-git/image-65.png)

You must be on the branch you're rebasing to perform a rebase.
![Switch to the branch to be rebased](screenshots-git/image-66.png)

![merged](screenshots-git/image-67.png)

## Task 4.2: Git Aliases & Productivity
1. Create useful aliases:
git st for status
git co for checkout
git br for branch
git lg for pretty log format

![aliases](screenshots-git/image-68.png)

## Task 5: Large Repository Management
1. Simulate large project:
Create multiple directories and files
Implement proper .gitignore for different file types

![ignore](screenshots-git/image-69.png)

Practice selective staging with git add -p

![-p](screenshots-git/image-70.png)

2. Repository maintenance:
Use git gc for cleanup
Understand repository size and optimization
Practice git prune and git fsck

- git fsck - Checks internal Git object integrity — like a file system check (fsck) for a hard drive.

![maintenance](screenshots-git/image-71.png)


## Task 5.2: Team Collaboration Scenario

1. Multi-contributor simulation:
Create a complex project structure
Simulate multiple developers working on different features
Practice conflict resolution in team settings
Implement code review processes

2. Branch protection rules:
Set up branch protection on GitHub
Require pull request reviews
Implement status checks
Test the protection rules


![alt text](screenshots-git/image-92.png)- main -intial commit

![merge ](screenshots-git/image-93.png)


![alt text](screenshots-git/image-94.png) - pull request of css

![alt text](screenshots-git/image-95.png) - merge conflict

![alt text](screenshots-git/image-96.png)

### Troubleshooting & Problem Solving

## Task 6.1: Common Git Problems

1. Simulate and solve problems:
Detached HEAD state

![detach](screenshots-git/image-72.png)

![new branch n main](screenshots-git/image-73.png)


Merge conflicts in binary files

![alt text](screenshots-git/image-74.png)

![alt text](screenshots-git/image-75.png)

![alt text](screenshots-git/image-76.png)

Accidentally committed sensitive data

![alt text](screenshots-git/image-77.png)

Lost commits recovery

![Step 1: Make a commit, then delete it](screenshots-git/image-78.png)

![Recover with reflog](screenshots-git/image-79.png)

![recover it](screenshots-git/image-80.png)

Corrupted repository repair

Simulate corruption - rm -rf .git/objects/??/
![Run a file system check](screenshots-git/image-81.png)

Try backup - git fetch origin
git reset --hard origin/main

2. Troubleshooting:
- Use git reflog to recover lost work

git reflog - shows the history of movements of HEAD, meaning it tracks every place your branch pointer has been — including commits you may have deleted, reset, or lost.

![reflog](screenshots-git/image-82.png)

- Practice git bisect for bug finding

git bisect uses binary search to find the commit that introduced a bug.

![bisect start](screenshots-git/image-83.png)

![end](screenshots-git/image-84.png)

# Why It’s Powerful
Instead of checking 100 commits one by one, git bisect only needs ~log₂(N) steps (i.e., 7 steps for 128 commits).

- Understand git fsck for repository health

- git fsck = File System Check
  
  ![fsck](screenshots-git/image-85.png)

## Task 6.2: Data Recovery & Forensics
1. Commit recovery:
Accidentally delete commits
Use reflog to recover
Practice hard reset recovery

![delete commits](screenshots-git/image-86.png)

![reflog](screenshots-git/image-88.png)

![recovery n merge ](screenshots-git/image-89.png)

2. File history analysis:

- Use git blame to track changes
- See Who Changed Each Line
- It helps track down which commit and author is responsible for each line in a file.

![blame](screenshots-git/image-90.png)

- Investigate file history with git log --follow

![log](screenshots-git/image-91.png)

## Task 6.3: Security & Best Practices
1. Security considerations:
Practice removing sensitive data
Implement signed commits
Understand security implications of different workflows

Workflow	                                                               Risk (if unmanaged)	Best Practice
Commit directly to main	Bugs or secrets added without review	- Use pull requests + branch protection
Push forcefully	Deletes history, can remove security changes	- Only allow force-push on non-protected branches
Share repo publicly	Can leak secrets in history	                - Clean history + use .gitignore
Merge untrusted PRs	Can introduce malicious code	            - Always review, test & sign commits
Share .git folder Leaks full history, secrets, branches         - Never share .git/ – only use remote


### Day 7: Project & Assessment
## Task 7.1: Complete Demo project

### 1. Repository Initialization:
- A new GitHub repository named `AIS_Task5.2` was created.

### 2. Collaborators Added:
- Team members were added as collaborators via GitHub repository settings.
- Everyone cloned the repository locally and set up remotes.

---
### 3. Git Workflow Followed:

#### ✅ Step 1: Initial Push
- One person created the main repo and performed the **initial push** with a `README.md` and empty folders/files.
- Commit message: `Initial project setup with base files`

#### ✅ Step 2: Feature Development Using Branches
- Separate branches were created for each part of the project:
- `feature/html` → Created `index.html`
- `feature/css` → Added styles in `style.css`
- `feature/js` → Implemented logic in `app.js`

#### ✅ Step 3: Pull Request & Code Review
- Each person pushed their feature branch and created a **Pull Request (PR)** on GitHub.
- One PR had **merge conflicts** due to simultaneous edits on the same file.

---

### 4. 🧩 Merge Conflict Resolution:
- The conflict occurred in and the developer resolved the conflict.
- Final version was tested, and the PR was successfully merged into `main`.
- Commit message: `Resolved merge conflict in index.html and finalized structure`

---

## 📘 Git Commands Practiced:
- `git clone`
- `git checkout -b feature-name`
- `git add`, `git commit -m`
- `git push origin feature-name`
- `git pull origin main`
- `git merge main`
- `git status`, `git diff`
- `git remote -v`
- Pull request creation and code review


![alt text](screenshots-git/image-92.png)- main -intial commit

![merge ](screenshots-git/image-93.png)


![alt text](screenshots-git/image-94.png) - pull request of css

![alt text](screenshots-git/image-95.png) - merge conflict

![alt text](screenshots-git/image-96.png)

![alt text](screenshots-git/image-97.png)

![alt text](screenshots-git/image-98.png)

![alt text](screenshots-git/image-99.png)

![alt text](screenshots-git/image-100.png)

![alt text](screenshots-git/image-101.png)

![alt text](screenshots-git/image-102.png)
