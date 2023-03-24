Author: IvAnlexn <“ivan.alexandrov1998@mail.ru/hdgit config --global user.email “ivan.alexandrov1998@mail.ru>
Date:   Thu Mar 16 12:30:44 2023 +0300

    initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

nothing added to commit but untracked files present (use "git add" to track)
(base) PS C:\Users\Ivan\Desktop\TestGit> git add .\Code.py
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git commit -m "New file .py"
[master 2b9634b] New file .py
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 Code.py
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
  (use "git push" to publish your local commits)

  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git add .\Code.py
[master 6a92f19] Hello World  added
 1 file changed, 1 insertion(+)
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
Revert "Added info in TestGit.md"
  (use "git restore <file>..." to discard changes in working directory)
        modified:   TestGit.md
no changes added to commit (use "git add" and/or "git commit -a")
(base) PS C:\Users\Ivan\Desktop\TestGit> git add .\TestGit.md
(base) PS C:\Users\Ivan\Desktop\TestGit> git commit -m "Added info in TestGit.md"
[master b710f42] Added info in TestGit.md
 1 file changed, 1 insertion(+)
b710f42 (HEAD -> master) Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git branch
(base) PS C:\Users\Ivan\Desktop\TestGit> git diff 2b9634b
diff --git a/Code.py b/Code.py
index e69de29..8e23576 100644
--- a/Code.py
+++ b/Code.py
Revert "Hello World  added"
+print("Hello World")
\ No newline at end of file
index e69de29..f58eb40 100644
--- a/TestGit.md
+++ b/TestGit.md
@@ -0,0 +1 @@
+# Code.py выводит на экран Hello World
\ No newline at end of file
Revert "New file .py"
[master 3798853] Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
 1 file changed, 1 deletion(-)
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
b710f42 Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git revert b710f42
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
nothing to commit, working tree clean
b710f42 Added info in TestGit.md
2b9634b New file .py
f4460f1 (origin/master) initial
[master da35603] Revert "Hello World  added" This reverts Hello World.
 1 file changed, 1 deletion(-)
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
da35603 (HEAD -> master) Revert "Hello World  added" This reverts Hello World.
3798853 Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
b710f42 Added info in TestGit.md
6a92f19 Hello World  added
(base) PS C:\Users\Ivan\Desktop\TestGit> git revert 2b9634b
[master 7305ac3] Revert "New file .py"
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 Code.py
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
3798853 Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
b710f42 Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git branch test
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --soft 7305ac3
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore 7305ac3
error: pathspec '7305ac3' did not match any file(s) known to git
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch test
7305ac3 (HEAD -> test, master) Revert "New file .py"
3798853 Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --soft da35603
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch test
  (use "git restore --staged <file>..." to unstage)
        deleted:    Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --soft b710f42
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --soft 2b9634b
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch test
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git restore
fatal: you must specify path(s) to restore
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore 3798853
error: pathspec '3798853' did not match any file(s) known to git
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
        deleted:    Code.py

(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
b710f42 Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset b710f42
Unstaged changes after reset:
D       Code.py
On branch test
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    Code.py
        modified:   TestGit.md

no changes added to commit (use "git add" and/or "git commit -a")
b710f42 (HEAD -> test) Added info in TestGit.md
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore
fatal: you must specify path(s) to restore
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore Code.py     
(base) PS C:\Users\Ivan\Desktop\TestGit> git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
7305ac3 (HEAD -> master) Revert "New file .py"
da35603 Revert "Hello World  added" This reverts Hello World.
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --soft da35603
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)

Changes to be committed:

(base) PS C:\Users\Ivan\Desktop\TestGit> git restore Code.py
error: pathspec 'Code.py' did not match any file(s) known to git
(base) PS C:\Users\Ivan\Desktop\TestGit> git checkout test        
error: Your local changes to the following files would be overwritten by checkout:
Please commit your changes or stash them before you switch branches.
Aborting
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)

(base) PS C:\Users\Ivan\Desktop\TestGit> git restore --staged Code.py
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
no changes added to commit (use "git add" and/or "git commit -a")
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore Code.py
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch master
Your branch is ahead of 'origin/master' by 5 commits.

(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
da35603 (HEAD -> master) Revert "Hello World  added" This reverts Hello World.
3798853 Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
b710f42 (test) Added info in TestGit.md
Revert "Hello World  added"
2b9634b New file .py
f4460f1 (origin/master) initial
Unstaged changes after reset:
M       Code.py
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git restore <file>..." to discard changes in working directory)

no changes added to commit (use "git add" and/or "git commit -a")
(base) PS C:\Users\Ivan\Desktop\TestGit> git restore .\Code.py
On branch master
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
Switched to branch 'test'
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
b710f42 (HEAD -> test) Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git revert 6a92f19
[test a87a917] Revert "Hello World  added"
 1 file changed, 1 deletion(-)
(base) PS C:\Users\Ivan\Desktop\TestGit> git status
On branch test
nothing to commit, working tree clean
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline 
a87a917 (HEAD -> test) Revert "Hello World  added"
b710f42 Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --hard b710f42
HEAD is now at b710f42 Added info in TestGit.md
(base) PS C:\Users\Ivan\Desktop\TestGit> git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 4 commits.
  (use "git push" to publish your local commits)
(base) PS C:\Users\Ivan\Desktop\TestGit> git log --oneline
3798853 (HEAD -> master) Revert "Added info in TestGit.md" This reverts commit b710f429bb9c6fa3f6e15a4f74eb54140a024123.
b710f42 (test) Added info in TestGit.md
6a92f19 Hello World  added
2b9634b New file .py
f4460f1 (origin/master) initial
(base) PS C:\Users\Ivan\Desktop\TestGit> git reset --hard b710f42
HEAD is now at b710f42 Added info in TestGit.md
(base) PS C:\Users\Ivan\Desktop\TestGit> 