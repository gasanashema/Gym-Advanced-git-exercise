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