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
gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase -i HEAD~2
[detached HEAD 8552d6d] Create Third and Fourth File
 Date: Fri Feb 28 14:18:08 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.
```

## 6 Dropping a Commit:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % touch unwanted.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add unwanted.txt  && git commit -m "Unwanted commit"
[main e9dc446] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
e9dc446 (HEAD -> main) Unwanted commit
8552d6d Create Third and Fourth File
f678ce1 chore: Combined multiple commits into one
gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase -i HEAD~1
Successfully rebased and updated refs/heads/main.

```

## 7. Reordering Commits:
```bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase -i --root
Successfully rebased and updated refs/heads/main.
```

## 8. Cherry-Picking Commits:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout -b ft/branch
Switched to a new branch 'ft/branch'
gymihumure@Ihumures-iMac Git_Advanced-exercises % echo "This is test 5" > test5.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add test5.md && git commit -m "Implemented test 5" 
[ft/branch bcb01ac] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
bcb01ac (HEAD -> ft/branch) Implemented test 5
8552d6d (main) Create Third and Fourth File
f678ce1 chore: Combined multiple commits into one
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Switched to branch 'main'
gymihumure@Ihumures-iMac Git_Advanced-exercises % git cherry-pick bcb01ac
[main 01d893e] Implemented test 5
 Date: Fri Feb 28 14:35:10 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
 ```
 ## 9. Visualizing Commit History (Bonus):
 ``` bash
 gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --graph --oneline --decorate --all
* 01d893e (HEAD -> main) Implemented test 5
| * bcb01ac (ft/branch) Implemented test 5
|/  
* 8552d6d Create Third and Fourth File
* f678ce1 chore: Combined multiple commits into one

```
## 10 Understanding Reflogs (Bonus):


## PART 2

## 1.Feature Branch Creation:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'
```

## 2.Working on the Feature Branch:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % echo "Another new feature" > feature.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add feature.txt && git commit -m "Implemented core functionality for new feautre"
[ft/new-feature da0626f] Implemented core functionality for new feautre
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt

 ```

 ## 3. Switching Back and Making More Changes:
 ``` bash
 gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Switched to branch 'main'
gymihumure@Ihumures-iMac Git_Advanced-exercises % echo "This is a readme file showing my contents" > readme.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add readme.txt && git commit -m "Updated project readme"
[main 0594de1] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
 ```

 ## 4. Local vs. Remote Branches and Branch Deletion:
 ``` bash
 gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Switched to branch 'main'
gymihumure@Ihumures-iMac Git_Advanced-exercises % echo "This is a readme file showing my contents" > readme.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git add readme.txt && git commit -m "Updated project readme"
[main 0594de1] Updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git status
On branch main
nothing to commit, working tree clean
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout ft/new-feature
Switched to branch 'ft/new-feature'
gymihumure@Ihumures-iMac Git_Advanced-exercises % git push origin ft/new-feature
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git remote -v
gymihumure@Ihumures-iMac Git_Advanced-exercises % git push origin ft/new-feature
fatal: 'origin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git remote add origin https://github.com/Ofallbrains/Git_Advanced-exercises.git

gymihumure@Ihumures-iMac Git_Advanced-exercises % git remove -v
git: 'remove' is not a git command. See 'git --help'.

The most similar command is
        remote
gymihumure@Ihumures-iMac Git_Advanced-exercises % git remote -v                 
origin  https://github.com/Ofallbrains/Git_Advanced-exercises.git (fetch)
origin  https://github.com/Ofallbrains/Git_Advanced-exercises.git (push)
gymihumure@Ihumures-iMac Git_Advanced-exercises % git push origin ft/new-feature
Enumerating objects: 11, done.
Counting objects: 100% (11/11), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (11/11), 914 bytes | 914.00 KiB/s, done.
Total 11 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), done.
To https://github.com/Ofallbrains/Git_Advanced-exercises.git
 * [new branch]      ft/new-feature -> ft/new-feature
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Switched to branch 'main'
gymihumure@Ihumures-iMac Git_Advanced-exercises % git pull origin main
fatal: couldn't find remote ref main
gymihumure@Ihumures-iMac Git_Advanced-exercises % git remote show origin

* remote origin
  Fetch URL: https://github.com/Ofallbrains/Git_Advanced-exercises.git
  Push  URL: https://github.com/Ofallbrains/Git_Advanced-exercises.git
  HEAD branch: ft/new-feature
  Remote branch:
    ft/new-feature tracked
  Local ref configured for 'git push':
    ft/new-feature pushes to ft/new-feature (up to date)
gymihumure@Ihumures-iMac Git_Advanced-exercises % git branch -r
  origin/ft/new-feature
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout -b main 
fatal: a branch named 'main' already exists
gymihumure@Ihumures-iMac Git_Advanced-exercises % git push -u origin main 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 318 bytes | 318.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote: 
remote: Create a pull request for 'main' on GitHub by visiting:
remote:      https://github.com/Ofallbrains/Git_Advanced-exercises/pull/new/main
remote: 
To https://github.com/Ofallbrains/Git_Advanced-exercises.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git remote show origin
* remote origin
  Fetch URL: https://github.com/Ofallbrains/Git_Advanced-exercises.git
  Push  URL: https://github.com/Ofallbrains/Git_Advanced-exercises.git
  HEAD branch: ft/new-feature
  Remote branches:
    ft/new-feature tracked
    main           tracked
  Local branch configured for 'git pull':
    main merges with remote main
  Local refs configured for 'git push':
    ft/new-feature pushes to ft/new-feature (up to date)
    main           pushes to main           (up to date)
gymihumure@Ihumures-iMac Git_Advanced-exercises % git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 feature.txt
gymihumure@Ihumures-iMac Git_Advanced-exercises % git push origin main
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (2/2), 302 bytes | 302.00 KiB/s, done.
Total 2 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/Ofallbrains/Git_Advanced-exercises.git
   0594de1..a688555  main -> main
gymihumure@Ihumures-iMac Git_Advanced-exercises % git branch -d ft/new-feature

Deleted branch ft/new-feature (was da0626f).
gymihumure@Ihumures-iMac Git_Advanced-exercises % git brainch -r
git: 'brainch' is not a git command. See 'git --help'.

The most similar command is
        branch

```

## 6. Creating a Branch from a Commit:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git branch
  ft/branch
* main
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline           
a688555 (HEAD -> main, origin/main) Merge branch 'ft/new-feature'
0594de1 Updated project readme
da0626f (origin/ft/new-feature) Implemented core functionality for new feautre
01d893e Implemented test 5
8552d6d Create Third and Fourth File
f678ce1 chore: Combined multiple commits into one
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout -b ft/new-branch-from-commit da0626f
Switched to a new branch 'ft/new-branch-from-commit'

```

## 7.Branch Merging:
## 8. Branch rebasing:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
gymihumure@Ihumures-iMac Git_Advanced-exercises % git rebase main
Successfully rebased and updated refs/heads/ft/new-branch-from-commit.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
545651f (HEAD -> main, origin/main, ft/new-branch-from-commit) Merge pull request #2 from Ofallbrains/ft/new-feature
691f9cb Merge pull request #1 from Ofallbrains/main
a688555 Merge branch 'ft/new-feature'
0594de1 Updated project readme
da0626f (origin/ft/new-feature, origin/ft/new-branch-from-commit) Implemented core functionality for new feautre
01d893e Implemented test 5
8552d6d Create Third and Fourth File
f678ce1 chore: Combined multiple commits into one

```

## 9. Renaming branches:
``` bash 
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout ft/new-branch-from-commit
Switched to branch 'ft/new-branch-from-commit'
gymihumure@Ihumures-iMac Git_Advanced-exercises % git branch -m ft/new-branch-from-commit ft/improved-branch-name

```
## 10 Checking Out Detached HEAD:
``` bash
gymihumure@Ihumures-iMac Git_Advanced-exercises % git log --oneline
545651f (HEAD -> ft/improved-branch-name, origin/main, main) Merge pull request #2 from Ofallbrains/ft/new-feature
691f9cb Merge pull request #1 from Ofallbrains/main
a688555 Merge branch 'ft/new-feature'
0594de1 Updated project readme
da0626f (origin/ft/new-feature, origin/ft/new-branch-from-commit) Implemented core functionality for new feautre
01d893e Implemented test 5
8552d6d Create Third and Fourth File
f678ce1 chore: Combined multiple commits into one
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout 691f9cb
Note: switching to '691f9cb'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 691f9cb Merge pull request #1 from Ofallbrains/main
gymihumure@Ihumures-iMac Git_Advanced-exercises % git checkout main
Previous HEAD position was 691f9cb Merge pull request #1 from Ofallbrains/main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
gymihumure@Ihumures-iMac Git_Advanced-exercises % 

```

## PART 3

## 1. Stashing changes

``` bash
PS E:\Moi\Git_Advanced-exercises> git stash  
Saved working directory and index state WIP on main: 545651f Merge pull request #2 from Ofallbrains/ft/new-feature
PS E:\Moi\Git_Advanced-exercises> git stash list
stash@{0}: WIP on main: 545651f Merge pull request #2 from Ofallbrains/ft/new-feature
PS E:\Moi\Git_Advanced-exercises> git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean        
PS E:\Moi\Git_Advanced-exercises> 

```

## 2. Retrieving stashed changes

``` bash
PS E:\Moi\Git_Advanced-exercises> git stash pop
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   feature.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (8e367a4a2aa8082e4f9ff9835cdd9bc6637d56ec)

```

## 3.Branch Merging conflicts:

``` bash
Switched to a new branch 'conflict-branch'
PS E:\Moi\Git_Advanced-exercises> git add . 
[conflict-branch 37ac637] modified feature file by adding
 1 file changed, 2 insertions(+)
PS E:\Moi\Git_Advanced-exercises> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS E:\Moi\Git_Advanced-exercises> git branch   
  conflict-branch
* main
PS E:\Moi\Git_Advanced-exercises> git checkout conflict-branch
Switched to branch 'conflict-branch'
PS E:\Moi\Git_Advanced-exercises> git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
PS E:\Moi\Git_Advanced-exercises> git add .
PS E:\Moi\Git_Advanced-exercises> git commit -m "Modified feature file by adding another test"
[main bc3c228] Modified feature file by adding another test
 1 file changed, 1 insertion(+)
PS E:\Moi\Git_Advanced-exercises> git merge conflict-branch
Auto-merging feature.txt
CONFLICT (content): Merge conflict in feature.txt
Automatic merge failed; fix conflicts and then commit the result.

```

## 6. Ignoring files/directories

``` bash

PS E:\Moi\Git_Advanced-exercises> echo "/tmp" > .gitignore

```

## 7. Working with tags and 8. deleting or removing tags

``` bash
PS E:\Moi\Git_Advanced-exercises> git tag v1.0
PS E:\Moi\Git_Advanced-exercises> git tag
v1.0
PS E:\Moi\Git_Advanced-exercises> git tag -d v1.0 
Deleted tag 'v1.0' (was 09273a2)

```

## 9. Pushing local changes to remote repositories

``` bash
PS E:\Moi\Git_Advanced-exercises> git add . 
PS E:\Moi\Git_Advanced-exercises> git commit -m "Created gitignore file"
[main 61ed2fe] Created gitignore file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .gitignore
PS E:\Moi\Git_Advanced-exercises> git push 
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.   
Delta compression using up to 4 threads 
Compressing objects: 100% (11/11), done.
Writing objects: 100% (12/12), 1.10 KiB | 140.00 KiB/s, done.
Total 12 (delta 5), reused 0 (delta 0), pack-reused 0        
remote: Resolving deltas: 100% (5/5), completed with 1 local object.
To https://github.com/Ofallbrains/Git_Advanced-exercises.git
   545651f..61ed2fe  main -> main

```

## 10 Pulling changes from the remote repositories

``` bash




    