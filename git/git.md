GIT Commands
------------
```
rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops
$ git init
Initialized empty Git repository in C:/Users/rathram/Desktop/Devops/.git/

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ ls .git/
HEAD  config  description  hooks/  info/  objects/  refs/

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git add 1.sh
warning: in the working copy of '1.sh', LF will be replaced by CRLF the next time Git touches it

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git add devops/

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   1.sh
        new file:   devops

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git diff
warning: in the working copy of '1.sh', LF will be replaced by CRLF the next time Git touches it
diff --git a/1.sh b/1.sh
index 2297580..9cc58b0 100644
--- a/1.sh
+++ b/1.sh
@@ -1,2 +1,2 @@
 a+b=c
-a-b=d
+

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   1.sh

no changes added to commit (use "git add" and/or "git commit -a")

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git add 1.sh
warning: in the working copy of '1.sh', LF will be replaced by CRLF the next time Git touches it

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git commit -m "this is my 2nd version which has substraction facility"
[master 98e899b] this is my 2nd version which has substraction facility
 1 file changed, 1 insertion(+)


rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git log
commit 98e899b09d30a1d8b0167e012fabe16f74bc130f (HEAD -> master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:51:47 2023 +0530

    this is my 2nd version which has substraction facility

commit 2d3c492161307c23bde7c041825d8a381e6145bb
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$

  
 rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git log
commit 1fb7911a25dca63edf908359af2c6e7d3c567d02 (HEAD -> master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:54:44 2023 +0530

    this is my  3rd version

commit 2d3c492161307c23bde7c041825d8a381e6145bb
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git reset --hard 2d3c492161307c23bde7c041825d8a381e6145bb
HEAD is now at 2d3c492 this is my first version'

```
