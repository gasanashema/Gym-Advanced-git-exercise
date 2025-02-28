# 1.Refinig git history
##  1. Missing file fix
```bash
gymgukunda@Gukundas-iMac TG-Shema-Projects % git clone git@github.com:gasanashema/Gym-Advanced-git-exercise.git
Cloning into 'Gym-Advanced-git-exercise'...
Enter passphrase for key '/Users/gymgukunda/.ssh/id_rsa': 
warning: You appear to have cloned an empty repository.
gymgukunda@Gukundas-iMac TG-Shema-Projects % cd Gym-Advanced-git-exercise 
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % touch test{1..4}.md
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add test1.md && git commit -m "chore: Create initial file"
[main (root-commit) 0812f48] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add test2.md && git commit -m "chore: Create another file"
[main f689a4e] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add test3.md && git commit -m "chore: Create third and fourth files"
[main fa48088] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git log
commit fa48088e7224b71a3213f8023a814f6d459573ed (HEAD -> main)
Author: gasanashema <shemaphilbert8@gmail.com>
Date:   Wed Feb 26 11:36:48 2025 +0200

    chore: Create third and fourth files
commit fa48088e7224b71a3213f8023a814f6d459573ed (HEAD -> main)
Author: gasanashema <shemaphilbert8@gmail.com>
Date:   Wed Feb 26 11:36:48 2025 +0200

    chore: Create third and fourth files

commit f689a4e25857e91cf31cb0d653c870f55371f339
Author: gasanashema <shemaphilbert8@gmail.com>
Date:   Wed Feb 26 11:36:39 2025 +0200

    chore: Create another file

commit 0812f4847b7dfc132fe26bdb680dbc61b7c00fb8
Author: gasanashema <shemaphilbert8@gmail.com>
Date:   Wed Feb 26 11:36:13 2025 +0200

    chore: Create initial file
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add test4.md
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit --amend -m 'create third and fourth file'
[main d28423c] create third and fourth file
 Date: Wed Feb 26 11:36:48 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
```
## 2.Editing Commit History

```bash 
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git rebase -i HEAD~2

[detached HEAD 3cb9bc9] Create second file
 Date: Wed Feb 26 11:36:48 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/ft/edit-commit-history.

```

## 3.Keeping History Tidy - Squashing Commits

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log
commit 8b513cd5f3050ee12d9609d5b5947da447f21e93 (HEAD -> dev, origin/dev)
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 16:16:45 2025 +0200

added answer 1.2 to the readme.md

commit 8963e2186fb21114d6a82efd4b62f5aa2be9d70f
Merge: b44aa46 5ab7534
Author: shema <106100022+gasanashema@users.noreply.github.com>
Date: Wed Feb 26 16:08:06 2025 +0200

Merge pull request #2 from gasanashema/ft/edit-commit-history

feat: edit commit history

commit 5ab7534adaae8f38b829b957c1f682222722f528
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 15:15:53 2025 +0200

added 1.1 answer to the readme.md file

commit 3cb9bc9ce3d59b7bcbe8a676a99c88aaee794f11
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 11:36:48 2025 +0200

Create second file

commit b44aa46d83c6c890b580193b3ff77a62f658a6d0
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 15:15:53 2025 +0200

added 1.1 answer to the readme.md file

commit d28423cfe1b0341efc57f278ae757216a00b2808
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 11:36:48 2025 +0200

create third and fourth file

commit f689a4e25857e91cf31cb0d653c870f55371f339
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 11:36:39 2025 +0200

chore: Create another file

commit 0812f4847b7dfc132fe26bdb680dbc61b7c00fb8
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 11:36:13 2025 +0200

chore: Create initial file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase -i commit 0812f4847b7dfc132fe26bdb680dbc61b7c00fb8
fatal: invalid upstream 'commit'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase -i 0812f4847b7dfc132fe26bdb680dbc61b7c00fb8
[detached HEAD f2f9978] create files added 1.1 answer to the readme.md file
Author: gasanashema <shemaphilbert8@gmail.com>
Date: Wed Feb 26 15:15:53 2025 +0200
1 file changed, 62 insertions(+)
create mode 100644 readme.md
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto 0812f48
Last commands done (5 commands done):
squash 3cb9bc9 Create second file
pick 5ab7534 added 1.1 answer to the readme.md file
(see more in file .git/rebase-merge/done)
Next command to do (1 remaining command):
pick 8b513cd added answer 1.2 to the readme.md
(use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'dev' on '0812f48'.
(all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply 5ab7534... added 1.1 answer to the readme.md file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
f2f9978 (HEAD) create files added 1.1 answer to the readme.md file
d28423c create third and fourth file
f689a4e chore: Create another file
0812f48 chore: Create initial file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$
```