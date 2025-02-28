## Part1

## 1 Missing File Fix:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % touch test{1..4}.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[main (root-commit) ac679ff] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[main 93eeb9c] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[main 69e1ae0] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git status                                               
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log
commit 69e1ae025b5971711727994a375edbf3e71b34a7 (HEAD -> main)
Author: Ofallbrains <ofallbrains@gmail.com>
Date:   Fri Feb 28 13:17:16 2025 +0200

    chore: Create third and fourth files

commit 93eeb9cf028c47af86a097092c3706ce5ef9c708
Author: Ofallbrains <ofallbrains@gmail.com>
Date:   Fri Feb 28 13:17:16 2025 +0200

    chore: Create another file

commit ac679ffc4313d4f283cf67d102182172921d756c
Author: Ofallbrains <ofallbrains@gmail.com>
Date:   Fri Feb 28 13:17:16 2025 +0200

    chore: Create initial file
    gymihumure@Ihumures-iMac Git_Advanced-exercises % git add test4.md && git commit -m "Created fourth file"
[main c5af508] Created fourth file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md

```


 ## 2 Editing Commit History:
 ``` bash
 gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase -i HEAD~2
[detached HEAD 0329982] chore: Create second  file
 Date: Fri Feb 28 13:17:16 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
cb9da58 (HEAD -> main) chore: Create third and fourth files
0329982 chore: Create second  file
ac679ff chore: Create initial file

```

## 3 Keeping History Tidy - Squashing Commits:
``` bash

gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase -i --root
[detached HEAD f678ce1] chore: Combined multiple commits into one
 Date: Fri Feb 28 13:38:54 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/main.

```

## 4 Splitting a Commit:

``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
29ccff1 (HEAD -> main) Created fourth file
4c60e87 chore: Create third and fourth files
f678ce1 chore: Combined multiple commits into one
gymihumure@Ihumures-iMac Git_Advanced-exercises % git reset --soft f678ce1
gymihumure@Ihumures-iMac Git_Advanced-exercises % git reset test4.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add .
gymihumure@Ihumures-iMac Git_Advanced-exercises % git reset test4.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git status
On branch main
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   test3.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

gymihumure@Ihumures-iMac Git_Advanced-exercises % git commit -m "Create Third File"

[main 9afb252] Create Third File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add test4.md
git commit -m "Create Fourth File"

[main 2b6a560] Create Fourth File
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test4.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
2b6a560 (HEAD -> main) Create Fourth File
9afb252 Create Third File
f678ce1 chore: Combined multiple commits into one
```

## 5 Advanced Squashing:
``` bash


    