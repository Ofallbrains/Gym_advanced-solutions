## Part1

## 1
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

```


 ## 2
 
    