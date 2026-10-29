\# Git Workflow and Interview Questions



\## 1. What is Git?



Git is a distributed version control system that records changes to files. Developers can work locally, maintain project history, create branches, and collaborate with others.



\## 2. What is the difference between merge and rebase?



\*\*Merge\*\* combines changes from one branch into another and normally creates a merge commit when needed. It preserves the existing branch history.



\*\*Rebase\*\* replays commits onto a new base commit, producing a more linear history. It rewrites commit history, so rebasing shared branches requires care.



\## 3. What is a pull request?



A pull request is a GitHub collaboration feature used to propose changes from one branch into another. It supports reviewing code, discussing changes, running checks, and merging after approval.



\## 4. How do you resolve merge conflicts?



1\. Run `git status` to identify conflicted files.

2\. Open each conflicted file.

3\. Resolve the sections marked with `<<<<<<<`, `=======`, and `>>>>>>>`.

4\. Save the corrected file.

5\. Stage the resolved file with `git add`.

6\. Complete the merge or rebase as appropriate.

7\. Run tests and inspect the final changes.



\## 5. What are Git tags?



Git tags mark specific commits, often to identify releases or milestones. An annotated tag includes metadata such as a message and tagger information.



Example:



```bash

git tag -a v1.0.0 -m "Task 4 completed"

git push origin v1.0.0

```



\## 6. What is a Git workflow?



A Git workflow is a repeatable process for managing changes. A common team workflow uses a stable `main` branch, a development integration branch, feature branches, pull requests, reviews, and merges.



\## 7. What is `git stash`?



`git stash` temporarily stores supported uncommitted changes so you can switch tasks without immediately committing them.



Examples:



```bash

git stash

git stash list

git stash pop

```



`git stash pop` reapplies the most recent stash and removes it from the stash list if successfully applied.



\## 8. What is the use of `.gitignore`?



`.gitignore` tells Git which untracked files and directories to ignore, such as logs, dependencies, generated output, and local environment files. It does not automatically untrack files that Git already tracks.



