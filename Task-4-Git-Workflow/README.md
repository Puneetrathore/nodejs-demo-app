\# Task 4: Version-Controlled DevOps Project with Git



\## Overview



This project demonstrates Git and GitHub best practices for managing a DevOps project. It covers branching strategies, feature development, pull requests, merging, tags, commit history, and repository documentation.



\## Objectives



\- Use Git for version control.

\- Maintain `main` and `dev` branches.

\- Create feature branches for individual changes.

\- Use GitHub pull requests to review and merge changes.

\- Practice merge conflict resolution.

\- Use `.gitignore` to exclude generated and unnecessary files.

\- Create Git tags to identify project versions.

\- Document Git commands and workflow concepts.



\## Branching Strategy



| Branch | Purpose |

|---|---|

| `main` | Stable, reviewed project version |

| `dev` | Integration branch for development |

| `feature/task4-documentation` | Implements Task 4 documentation |



\## Git Workflow



1\. Create a feature branch from `dev`.

2\. Make a focused change.

3\. Stage and commit the changes with a meaningful message.

4\. Push the feature branch to GitHub.

5\. Open a pull request targeting `dev`.

6\. Review and merge the pull request.

7\. Open a pull request from `dev` to `main` when the work is ready.

8\. Create a version tag for the completed milestone.



\## Commands Practiced



```bash

git status

git branch

git switch -c dev

git switch -c feature/task4-documentation

git add .

git commit -m "Add Task 4 documentation"

git push -u origin feature/task4-documentation

git log --oneline --graph --all

git tag -a v1.0.0 -m "Task 4 completed"

git push origin v1.0.0

```



\## Repository Hygiene



The `.gitignore` file excludes generated files, editor settings, logs, and local secrets that should not be committed.



\## Learning Outcomes



\- Understand distributed version control with Git.

\- Manage changes using branches and commits.

\- Collaborate through pull requests.

\- Understand merge conflicts, rebasing, and merging.

\- Track releases with Git tags.

\- Maintain a clean repository using `.gitignore`.



\## Interview Questions



See \[`docs/git-workflow.md`](docs/git-workflow.md) for explanations of the eight required Git interview questions.



\## Author



Puneet Rathore



GitHub: https://github.com/Puneetrathore



