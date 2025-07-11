### Section 1: Foundation & Local Repository
## Task 1.1: Environment Setup & Configuration
1. Setup Git Bash/Terminal
2. Repository Creation

![alt text](image.png)

## Task 1.2: Basic File Operations
1. Create and commit files:
![alt text](image-1.png)

![alt text](image-2.png)

2. Practice staging
![alt text](image-3.png)

![alt text](image-4.png)

![alt text](image-5.png)

git diff - This command shows the difference between the working directory and the staging area.

![alt text](image-6.png)

## Task 1.3: History and Undoing Changes

1. Explore Git history:

- git log --oneline
Shows a compact log with each commit in one line:

![alt text](image-7.png)

- git log --graph
Displays the branch and merge history as a graph:

![alt text](image-8.png)

- git log --decorate
Adds branch/tag names to commits:

![alt text](image-9.png)


2. Practice undoing changes:
- Make a "bad" commit (add wrong content)
![alt text](image-12.png)

- Practice git revert to undo it
git revert <commit-hash>
![alt text](image-13.png)

- Make another change and practice git reset
![alt text](image-14.png)

git reset --soft <hash>     : Uncommit, keep changes staged

![alt text](image-15.png)

git reset --mixed <hash>	: Uncommit, changes unstaged

![alt text](image-16.png)

git reset --hard <hash>     : Uncommit and delete changes completely

![alt text](image-12.png)



- Document the differences between revert and reset
🔁 git revert                                              vs                                        git reset

Purpose	Undo a specific commit by creating a new commit	                   Move the current branch to a previous commit (and maybe remove changes)
History-safe?	✅ Yes (safe for shared/public repos)	                 ❌ No (can rewrite history — unsafe for shared branches)
Creates a new commit? ✅ Yes      	                                     ❌ No (unless used with --soft, then commit can follow)
Data loss risk?	❌ Low	                                                 ⚠️ High (with --hard, deletes changes permanently)
Common use :Undo changes without affecting commit history	               Rewind history or unstage/remove local commits
Best for :	Public/shared repositories	                                   Private/local branches or fixing recent mistakes


## Task 1.4: File Management
1. Gitignore:

![alt text](image-10.png)

2. File removal:

![alt text](image-11.png)

📄 Check out the [Git Cheat Sheet](GitCheatSheet.md)

### Section 2: Branching & Merging Mastery
## Task 2.1: Branch Creation & Management
1. Create feature branches:


