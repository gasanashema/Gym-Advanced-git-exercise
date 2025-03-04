# Part 1: Refining Git History (10 Challenges)
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

## 8. Cherry Picking

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ touch test5.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git add .
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git commit -m 'Implemented test 5'
[ft/branch a037941] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
a037941 (HEAD -> ft/branch) Implemented test 5
da8743e (origin/dev, dev) Merge pull request #19 from gasanashema/reopen/ft
6166aee (origin/reopen/ft) re-order commits
870efbf re-order commits
afe894e create third file

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git checkout dev
Switched to branch 'dev'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git cherry-pick a037941
[dev 0361f32] Implemented test 5
 Date: Mon Mar 3 17:00:23 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --oneline
0361f32 (HEAD -> dev) Implemented test 5
da8743e (origin/dev) Merge pull request #19 from gasanashema/reopen/ft
6166aee (origin/reopen/ft) re-order commits
870efbf re-order commits
afe894e create third file
c04b9f8 Merge pull request #13 from gasanashema/ft/drop-commit
1dca356 (origin/ft/drop-commit) Drop a commit
4468e6a Merge pull request #12 from gasanashema/adv-squash
cfbeedd (origin/adv-squash) advenced squash

```

## 9. Visualizing Commit History

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git checkout -b commit-history
Switched to a new branch 'commit-history'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git log --graph
*   commit 41e026a6b7ea3c29fb1c458b8d4875c4344ab730 (HEAD -> commit-history, origin/dev, dev)
|\  Merge: da8743e 68a5236
| | Author: shema <106100022+gasanashema@users.noreply.github.com>
| | Date:   Mon Mar 3 17:22:41 2025 +0200
| | 
| |     Merge pull request #20 from gasanashema/ft/branch
| |     
| |     Cherry Picking
| | 
| * commit 68a5236de8a185d99540595b2665bcaa01d968e1 (ft/branch)
| | Author: Shema <shemaphilbert8@gmail.com>
| | Date:   Mon Mar 3 17:20:34 2025 +0200
| | 
| |     Cherry Picking
| | 
| * commit a03794181c6f5418ae20be4a9d5d412a221a1ed9
|/  Author: Shema <shemaphilbert8@gmail.com>
|   Date:   Mon Mar 3 17:00:23 2025 +0200
|   
|       Implemented test 5
|   
*   commit da8743e8a75e5840d1e7ee2aece428621e47c36c
|\  Merge: c04b9f8 6166aee
| | Author: shema <106100022+gasanashema@users.noreply.github.com>
| | Date:   Mon Mar 3 16:40:53 2025 +0200
| | 
| |     Merge pull request #19 from gasanashema/reopen/ft
| |     
| |     Re-order commits
| |   
| *   commit 6166aeef695f1afde3e7ed346131cf7ca6981ac1 (origin/reopen/ft)
| |\  Merge: 870efbf c04b9f8
| |/  Author: Shema <shemaphilbert8@gmail.com>
|/|   Date:   Mon Mar 3 16:19:58 2025 +0200
| |   
| |       re-order commits
| |   
* |   commit c04b9f83cf4b4924cd9f91ebbd3d101e0899aaf0
|\ \  Merge: 4468e6a 1dca356
| | | Author: shema <106100022+gasanashema@users.noreply.github.com>
| | | Date:   Mon Mar 3 14:03:56 2025 +0200
| | | 
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ 

```

## 10. Understanding Reflogs

```bash

shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git checkout -b reflog/ft
Switched to a new branch 'reflog/ft'
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ git reflog
4a06c2e (HEAD -> reflog/ft, origin/dev, dev) HEAD@{0}: checkout: moving from dev to reflog/ft
4a06c2e (HEAD -> reflog/ft, origin/dev, dev) HEAD@{1}: pull --rebase origin dev: Fast-forward
41e026a HEAD@{2}: checkout: moving from commit-history to dev
1e1a407 (origin/commit-history) HEAD@{3}: commit: Visualizing commit history
41e026a HEAD@{4}: checkout: moving from dev to commit-history
41e026a HEAD@{5}: pull --rebase origin dev (finish): returning to refs/heads/dev
41e026a HEAD@{6}: pull --rebase origin dev (start): checkout 41e026a6b7ea3c29fb1c458b8d4875c4344ab730
0361f32 HEAD@{7}: checkout: moving from ft/branch to dev
68a5236 (ft/branch) HEAD@{8}: commit: Cherry Picking
a037941 HEAD@{9}: checkout: moving from dev to ft/branch
0361f32 HEAD@{10}: cherry-pick: Implemented test 5
da8743e HEAD@{11}: checkout: moving from ft/branch to dev
a037941 HEAD@{12}: commit: Implemented test 5
da8743e HEAD@{13}: checkout: moving from dev to ft/branch
shema@shema:~/New Volume data/The Gym/Projects/Gym-Advanced-git-exercise$ 

```

# Part 2: Branching Basics (10 Challenges)

## 1.Feature Branch Creation

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```
## 2. Working on the Feature Branch

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % echo 'hello world'>feature.txt
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'Implemented core functionality for new feature'
[ft/new-feature 241fe5e] Implemented core functionality for new feature
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```

## 3. Switching Back and Making More Changes

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % echo 'some content here'>readme.txt
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'Updated project readme'
[dev aa838cc] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

```

## 4. Local vs. Remote Branches

```bash 

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git branch -r     

  origin/dev
  origin/ft/edit-commit-history
  origin/ft/new-feature
  origin/ft/split-commit
  origin/main
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git fetch origin

Enter passphrase for key '/Users/gymgukunda/.ssh/id_rsa': 
remote: Enumerating objects: 5, done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 5 (from 1)
Unpacking objects: 100% (5/5), 4.30 KiB | 733.00 KiB/s, done.
From github.com:gasanashema/Gym-Advanced-git-exercise
 * [new branch]      ft/branch  -> origin/ft/branch
   d28423c..9bf8d36  main       -> origin/main

```
## 5. Branch Deletion

```bash
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git pull --rebase origin dev
Enter passphrase for key '/Users/gymgukunda/.ssh/id_rsa': 
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 911 bytes | 455.00 KiB/s, done.
From github.com:gasanashema/Gym-Advanced-git-exercise
 * branch            dev        -> FETCH_HEAD
   bcdbc73..e8830ac  dev        -> origin/dev
Successfully rebased and updated refs/heads/dev.
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git branch -D ft/new-feature
Deleted branch ft/new-feature (was efce9a1).
```

## 6. Creating a branch from commit
```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git log --oneline
3b47e81 (HEAD -> dev, origin/dev) Branch Deletion
a97a3a2 Updated project readme
e8830ac Merge pull request #25 from gasanashema/ft/new-feature
efce9a1 (origin/ft/new-feature) Local vs Remote
326d887 working on feature branch
241fe5e Implemented core functionality for new feature
48d11cf Feature Branch Creation
bcdbc73 Merge pull request #23 from gasanashema/reflog/ft
1dfc03b Understanding reflogs
4a06c2e Merge pull request #22 from gasanashema/commit-history
1e1a407 Visualizing commit history
41e026a Merge pull request #20 from gasanashema/ft/branch
68a5236 Cherry Picking
a037941 Implemented test 5
da8743e Merge pull request #19 from gasanashema/reopen/ft
6166aee re-order commits
870efbf re-order commits
afe894e create third file
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout -b ft/branch-from-commit 326d887
Switched to a new branch 'ft/branch-from-commit'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```
## 7. Branch Merging

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git branch
  dev
* ft/branch-from-commit
  main
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git merge dev
Already up to date.
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git merge ft/branch-from-commit
Updating 3b47e81..9c39886
Fast-forward
 readme.md | 28 ++++++++++++++++++++++++++++
 1 file changed, 28 insertions(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```

## 8.Branch Rebasing

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout ft/branch-from-commit 

Switched to branch 'ft/branch-from-commit'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git rebase dev
Successfully rebased and updated refs/heads/ft/branch-from-commit.
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```

## 9. Branch Rename
```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git pull --rebase origin dev
Enter passphrase for key '/Users/gymgukunda/.ssh/id_rsa': 
Enter passphrase for key '/Users/gymgukunda/.ssh/id_rsa': 
remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (1/1), 910 bytes | 455.00 KiB/s, done.
From github.com:gasanashema/Gym-Advanced-git-exercise
 * branch            dev        -> FETCH_HEAD
   3ab916c..e195e85  dev        -> origin/dev
Updating 3ab916c..e195e85
Fast-forward
 readme.md | 13 +++++++++++++
 1 file changed, 13 insertions(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git branch -m ft/branch-from-commit ft/improved-branch-name
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise %       

```

## 10.Checking Out Detached HEAD

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git log --oneline
e3e9a4a (HEAD -> dev, origin/dev) Merge pull request #29 from gasanashema/ft/improved-branch-name
004d112 (origin/ft/improved-branch-name, ft/improved-branch-name) Branch Rename
e195e85 Merge pull request #28 from gasanashema/ft/branch-from-commit
898fbee (origin/ft/branch-from-commit) Branch Rebasing
3ab916c Merge pull request #27 from gasanashema/ft/branch-from-commit
0e97121 Merging Branches
17a5fcc Merge pull request #26 from gasanashema/ft/branch-from-commit
9c39886 Creating a branch from a commit
3b47e81 Branch Deletion
a97a3a2 Updated project readme
e8830ac Merge pull request #25 from gasanashema/ft/new-feature
efce9a1 (origin/ft/new-feature) Local vs Remote
326d887 working on feature branch
241fe5e Implemented core functionality for new feature
48d11cf Feature Branch Creation
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout 0e97121
Note: switching to '0e97121'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 0e97121 Merging Branches
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git status
HEAD detached at 0e97121
nothing to commit, working tree clean
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % echo "Temporary changes" >> temp.txt

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add temp.txt
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m "Testing detached HEAD"
[detached HEAD 643649e] Testing detached HEAD
 1 file changed, 1 insertion(+)
 create mode 100644 temp.txt
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout -b new-branch-from-detached
Switched to a new branch 'new-branch-from-detached'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise %     

```

# Part 3: Advanced Workflows (10+ Challenges)
## 1.Stashing Changes
```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git stash
Saved working directory and index state WIP on dev: 44b2d68 Merge pull request #30 from gasanashema/new-branch-from-detached
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```

## 2.Retrieving Stashed Changes
```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git stash pop
On branch dev
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   readme.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (1421a886d606e2dbe8c954262598aae33379fb97)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

#comment
#not a comment
```
## 3.Branch Merging Conflicts (Continued)

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
M       readme.md
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'added message'
[ft/improved-branch-name 1be0faf] added message
 1 file changed, 1 insertion(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'added message also to make conflicts'
[dev aefb291] added message also to make conflicts
 1 file changed, 1 insertion(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout ft/improved-branch-name                
Switched to branch 'ft/improved-branch-name'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git merge dev                                       
Auto-merging readme.md
CONFLICT (content): Merge conflict in readme.md
Automatic merge failed; fix conflicts and then commit the result.
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'conflicts resolved'
[ft/improved-branch-name 0ec127a] conflicts resolved

```
## 4.Resolving Merge Conflicts with a Merge Tool

```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
M       readme.md
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout ft/improved-branch-name
Switched to branch 'ft/improved-branch-name'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'added message'
[ft/improved-branch-name 1be0faf] added message
 1 file changed, 1 insertion(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'added message also to make conflicts'
[dev aefb291] added message also to make conflicts
 1 file changed, 1 insertion(+)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout ft/improved-branch-name                
Switched to branch 'ft/improved-branch-name'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git merge dev                                       
Auto-merging readme.md
CONFLICT (content): Merge conflict in readme.md
Automatic merge failed; fix conflicts and then commit the result.
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'conflicts resolved'
[ft/improved-branch-name 0ec127a] conflicts resolved

```

## 5.Understanding Detached HEAD State
```bash

gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git log --oneline   
3fbcb82 (HEAD -> dev, origin/dev) Resolving Merge Conflicts with a Merge Tool
7d73e47 Merge pull request #31 from gasanashema/ft/improved-branch-name
c6f2d9c (origin/ft/improved-branch-name, ft/improved-branch-name) conflicts resolved
0ec127a conflicts resolved
aefb291 added message also to make conflicts
1be0faf added message
5d1e81d Stashing
44b2d68 Merge pull request #30 from gasanashema/new-branch-from-detached
ac17922 (origin/new-branch-from-detached, new-branch-from-detached) Checking Out Detached HEAD
2ed4c84 Merge branch 'ft/improved-branch-name' into new-branch-from-detached
643649e Testing detached HEAD
e3e9a4a Merge pull request #29 from gasanashema/ft/improved-branch-name
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout 1be0faf
Note: switching to '1be0faf'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 1be0faf added message
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
error: Your local changes to the following files would be overwritten by checkout:
        readme.md
Please commit your changes or stash them before you switch branches.
Aborting
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git add .
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git commit -m 'unwanted changes'
[detached HEAD a415c58] unwanted changes
 1 file changed, 1 insertion(+), 1 deletion(-)
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % git checkout dev
Warning: you are leaving 1 commit behind, not connected to
any of your branches:

  a415c58 unwanted changes

If you want to keep it by creating a new branch, this may be a good time
to do so with:

 git branch <new-branch-name> a415c58

Switched to branch 'dev'
gymgukunda@Gukundas-iMac Gym-Advanced-git-exercise % 

```