# Git Interview Questions and Answers

---

## 1. What is Git?
Git is a **distributed version control system (VCS)** that tracks changes in source code during software development. It allows multiple developers to work on a project simultaneously.

---

## 2. What is the difference between Git and GitHub?
- **Git**: A version control system.
- **GitHub**: A web-based platform to host and manage Git repositories.

---

## 3. What is the abbreviation of VCS?
**VCS**: Version Control System

---

## 4. What is the abbreviation of SCM?
**SCM**: Source Code Management

---

## 5. Five SCM Tools
1. Git  
2. SVN (Subversion)  
3. Mercurial  
4. Perforce  
5. CVS (Concurrent Versions System)

---

## 6. What is a Branch?
A branch is a lightweight movable pointer to a commit. It allows you to work on different versions of the project simultaneously.

```bash
git branch feature-xyz
```

---

## 7. What is a Tag?
A tag is a reference to a specific commit used mainly for marking release points.

```bash
git tag v1.0
```

---

## 8. Branch vs Tag
| Feature      | Branch                | Tag                  |
|--------------|------------------------|-----------------------|
| Purpose      | Development line       | Marking releases      |
| Movable      | Yes                    | No                    |
| Commands     | `git branch`           | `git tag`             |

---

## 9. When to Create Branch/Tag
- **Branch**: For new features or bug fixes
- **Tag**: To mark a version/release

---

## 10. What does `git add` do?
It adds changes from the working directory to the staging area.

```bash
git add <filename>
```

---

## 11. Command to revert code from staging area to working area
```bash
git reset <filename>
```

---

## 12. What is `git revert`?
Creates a new commit that undoes the changes of a previous commit.

```bash
git revert <commit_id>
```

---

## 13. Difference Between Fetch and Pull
- `git fetch`: Downloads changes from remote but doesn't merge.
- `git pull`: Fetches and merges in one command.

---

## 14. View Available Branches
```bash
git branch
```

---

## 15. Create a Branch
```bash
git branch new-branch
```

---

## 16. Switch Between Branches
```bash
git checkout branch-name
```

---

## 17. Create & Switch to Branch in One Command
```bash
git checkout -b new-branch
```

---

## 18. Delete Local Branch
```bash
git branch -d branch-name
```

---

## 19. Delete Remote Branch
```bash
git push origin --delete branch-name
```

---

## 20. Branching Strategy
- Git Flow
- Feature Branching
- Trunk-based development

---

## 21. What is `git stash`?
Temporarily saves changes that are not committed.

```bash
git stash
```

---

## 22. What is `git cherry-pick`?
Apply a specific commit from another branch.

```bash
git cherry-pick <commit-id>
```

---

## 23. What is `git rebase`?
Moves or combines a sequence of commits to a new base commit.

```bash
git rebase main
```

---

## 24. What is PAT?
**Personal Access Token** - used for authenticating to GitHub instead of passwords.

---

## 25. What is SSH Key & How to Generate
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

---

## 26. Default SSH Key Path
`~/.ssh/id_rsa` and `~/.ssh/id_rsa.pub`

---

## 27. How Many Files are Created in SSH Key
Two files:
- `id_rsa` (Private key)
- `id_rsa.pub` (Public key)

---

## 28. Git vs GitHub (Again)
Refer to answer #2.

---

## 29. Git Commit Best Practices
- Use meaningful messages
- Use present tense
- Keep the message short (50 chars summary)
- Separate subject from body with a blank line

---

## 30. Change Commit Message After Push (If no one pulled)
```bash
git commit --amend -m "New message"
git push --force
```

---

## 31. Rename a Branch
```bash
git branch -m old-name new-name
```

---

## 32. Get Code from Remote
```bash
git clone <repo-url>
```

---

## 33. Check Particular Branch on GitHub
Use the branch dropdown in GitHub UI or:
```bash
git ls-remote --heads origin
```

---

## 34. View All Git Commit Messages
```bash
git log
```

---

## 35. Create a Git Repository
```bash
git init
```

---

## 36. Check if Branch is Merged
```bash
git branch --merged
```

---

## 37. What is SubGit?
A tool to migrate projects from Subversion (SVN) to Git.

---

## 38. Git Language
Git is developed in **C**.

---

## 39. Git Merge vs Rebase
- **Merge**: Preserves history; creates a merge commit.
- **Rebase**: Rewrites history; no merge commit.

---

## 40. Git Reset vs Git Revert
- **Reset**: Moves HEAD to a previous commit (can erase history).
- **Revert**: Creates a new commit to undo previous commit.

---

## 41. Git Workflow
- Clone repo
- Create branch
- Add code
- Commit changes
- Push branch
- Create PR
- Review & Merge

---

## 42. Migrate from SVN to GitHub
Use SubGit or `git svn` commands to import SVN project and push to GitHub.

---

## 43. What is Merge Conflict?
Occurs when two branches have changes on the same lines. Must resolve manually.

---

## 44. Check Files in a Commit
```bash
git show --stat <commit-id>
```

---

## 45. Git Hooks
Scripts triggered by git events.
Examples:
- pre-commit
- pre-push
- post-merge

---

## 46. .gitignore File
Specifies intentionally untracked files to ignore.

Example:
```
node_modules/
.env
*.log
```

---

## 47. Git Bare vs Non-Bare Repo
- **Bare**: No working directory (used as central repo)
- **Non-Bare**: Normal repo with working tree

---

## 48. Git Archive Command
Create archive:
```bash
git archive -o archive.zip HEAD
```

---

## 49. Git Prune, Mirror, Repack
- `git prune`: Remove unreachable objects
- `git clone --mirror`: Full mirror of a repo
- `git repack`: Compress pack files for storage

---

## 50. Git Objects
- **Blob**: File data
- **Tree**: Directory listing
- **Commit**: Snapshot pointer
- **Tag**: Named pointer

---