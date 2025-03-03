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
##  4.Spliting a commit

```bash
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
c496aae (HEAD -> ft/split-commit, origin/ft/split-commit, origin/dev, dev) feat: Keeping History Tidy - Squashing Commits
cb51692 (origin/ft/squashing, ft/squashing) 1.3 Keeping History Tidy - Squashing Commits
fc6b384 Create files
8b513cd added answer 1.2 to the readme.md
8963e21 Merge pull request #2 from gasanashema/ft/edit-commit-history
5ab7534 added 1.1 answer to the readme.md file
3cb9bc9 Create second file
b44aa46 added 1.1 answer to the readme.md file
d28423c create third and fourth file
f689a4e chore: Create another file
0812f48 chore: Create initial file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase -i d28423c^
Stopped at d28423c...  create third and fourth file
You can amend the commit now, with

  git commit --amend 

Once you are satisfied with your changes, run

  git rebase --continue
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git reset HEAD^
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git add test3.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit -m 'create third file'
[detached HEAD 05f9a08] create third file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git add test4.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit -m 'create fourth file'
[detached HEAD 7df66c2] create fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git branch
* (no branch, rebasing ft/split-commit)
  dev
  ft/split-commit
  ft/squashing
  main
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase --continue
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto f689a4e
Last commands done (3 commands done):
   pick fc6b384 Create files
   pick b44aa46 added 1.1 answer to the readme.md file
  (see more in file .git/rebase-merge/done)
Next commands to do (3 remaining commands):
   pick 3cb9bc9 Create second file
   pick 5ab7534 added 1.1 answer to the readme.md file
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'ft/split-commit' on 'f689a4e'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply b44aa46... added 1.1 answer to the readme.md file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit --allow-empty
Aborting commit due to empty commit message.
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit --allow-empty
[detached HEAD 91b50ee] added 1.1 answer to the readme.md file
 Author: gasanashema <shemaphilbert8@gmail.com>
 Date: Wed Feb 26 15:15:53 2025 +0200

```

## 5. Advenced Squashing

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
2071eaa (HEAD -> advanced-squash, origin/dev, dev) Merge pull request #8 from gasanashema/ft/split
057314e (origin/ft/split) Split commit
0bec9d8 spliting a commit
91b50ee added 1.1 answer to the readme.md file
c23ccc6 Create files
7df66c2 create fourth file
05f9a08 create third file
c496aae (origin/ft/split-commit) feat: Keeping History Tidy - Squashing Commits
cb51692 (origin/ft/squashing) 1.3 Keeping History Tidy - Squashing Commits
fc6b384 Create files
8b513cd added answer 1.2 to the readme.md
8963e21 Merge pull request #2 from gasanashema/ft/edit-commit-history
5ab7534 added 1.1 answer to the readme.md file
3cb9bc9 Create second file
b44aa46 added 1.1 answer to the readme.md file
d28423c create third and fourth file
f689a4e chore: Create another file
0812f48 chore: Create initial file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ ^C
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase -i 05f9a08^
[detached HEAD 259e319] create third and fourth file
 Date: Mon Mar 3 11:24:20 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto f689a4e
Last commands done (6 commands done):
   pick 0bec9d8 spliting a commit
   pick d28423c create third and fourth file
  (see more in file .git/rebase-merge/done)
Next commands to do (5 remaining commands):
   pick fc6b384 Create files
   pick b44aa46 added 1.1 answer to the readme.md file
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'advanced-squash' on 'f689a4e'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply d28423c... create third and fourth file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline --graph --decorate
* 3ca3995 (HEAD) spliting a commit
* fd66353 added 1.1 answer to the readme.md file
* c750b59 Create files
* 259e319 create third and fourth file
* f689a4e chore: Create another file
* 0812f48 chore: Create initial file

```

## 6. Drop a commit

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git checkout -b ft/drop-commit
Switched to a new branch 'ft/drop-commit'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ touch unwanted.txt
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git add .
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit -m 'Unwanted commit'
[ft/drop-commit 4c78629] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git reset --hard HEAD~1
HEAD is now at 4468e6a Merge pull request #12 from gasanashema/adv-squash
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$
```

## 7. Re-order commits

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
c04b9f8 (HEAD -> ft/reorder-commits, origin/dev, dev) Merge pull request #13 from gasanashema/ft/drop-commit
1dca356 (origin/ft/drop-commit) Drop a commit
4468e6a Merge pull request #12 from gasanashema/adv-squash
cfbeedd (origin/adv-squash) advenced squash
5c5a133 advenced spuash
3ca3995 spliting a commit
fd66353 added 1.1 answer to the readme.md file
c750b59 Create files
259e319 create third and fourth file
2071eaa (origin/advanced-squash) Merge pull request #8 from gasanashema/ft/split
057314e (origin/ft/split) Split commit
0bec9d8 spliting a commit
91b50ee added 1.1 answer to the readme.md file
c23ccc6 Create files
7df66c2 create fourth file
05f9a08 create third file
c496aae (origin/ft/split-commit) feat: Keeping History Tidy - Squashing Commits
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase -i 5c5a133^
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto 3ca3995
Last commands done (2 commands done):
   pick 5c5a133 advenced spuash
   pick 7df66c2 create fourth file
Next commands to do (11 remaining commands):
   pick 05f9a08 create third file
   pick c23ccc6 Create files
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'ft/reorder-commits' on '3ca3995'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply 7df66c2... create fourth file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
5c5a133 (HEAD) advenced spuash
3ca3995 spliting a commit
fd66353 added 1.1 answer to the readme.md file
c750b59 Create files
259e319 create third and fourth file
f689a4e chore: Create another file
0812f48 chore: Create initial file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit
interactive rebase in progress; onto 3ca3995
Last commands done (2 commands done):
   pick 5c5a133 advenced spuash
   pick 7df66c2 create fourth file
Next commands to do (11 remaining commands):
   pick 05f9a08 create third file
   pick c23ccc6 Create files
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'ft/reorder-commits' on '3ca3995'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase skip
fatal: It seems that there is already a rebase-merge directory, and
I wonder if you are in the middle of another rebase.  If that is the
case, please try
        git rebase (--continue | --abort | --skip)
If that is not the case, please
        rm -fr ".git/rebase-merge"
and run me again.  I am stopping in case you still have something
valuable there.

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git rebase --continue
The previous cherry-pick is now empty, possibly due to conflict resolution.
If you wish to commit it anyway, use:

    git commit --allow-empty

Otherwise, please use 'git rebase --skip'
interactive rebase in progress; onto 3ca3995
Last commands done (3 commands done):
   pick 7df66c2 create fourth file
   pick 05f9a08 create third file
  (see more in file .git/rebase-merge/done)
Next commands to do (10 remaining commands):
   pick c23ccc6 Create files
   pick 91b50ee added 1.1 answer to the readme.md file # empty
  (use "git rebase --edit-todo" to view and edit)
You are currently rebasing branch 'ft/reorder-commits' on '3ca3995'.
  (all conflicts fixed: run "git rebase --continue")

nothing to commit, working tree clean
Could not apply 05f9a08... create third file
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit --allow-empty
[detached HEAD afe894e] create third file
 Date: Mon Mar 3 11:24:20 2025 +0200
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git push origin 

```