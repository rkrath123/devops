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


rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git remote -v


$ git remote add -h
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=(push|fetch)]
                          set up remote as a mirror to push to or fetch from


rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ cat 1.sh
a+b=c
a-b=d

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git status
On branch master
nothing to commit, working tree clean

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git checkout -b multipication
Switched to a new branch 'multipication'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$ cat 1.sh

a+b=c
a-b=d
a*b=e

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$ git add .

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$ git commit -m "multipication"
[multipication 02d3c06] multipication
 1 file changed, 2 insertions(+)

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$ git log
commit 02d3c061dee1985f8504b759fe109eae7acd2a64 (HEAD -> multipication)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 17:00:29 2023 +0530

    multipication

commit 2d3c492161307c23bde7c041825d8a381e6145bb (master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (multipication)
$
rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git log multipication
commit 02d3c061dee1985f8504b759fe109eae7acd2a64 (multipication)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 17:00:29 2023 +0530

    multipication

commit 2d3c492161307c23bde7c041825d8a381e6145bb (HEAD -> master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)


$ git log
commit 2d3c492161307c23bde7c041825d8a381e6145bb (HEAD -> master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$


rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git cherry-pick 02d3c061dee1985f8504b759fe109eae7acd2a64
[master e495ec6] multipication
 Date: Fri May 26 17:00:29 2023 +0530
 1 file changed, 2 insertions(+)

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git log
commit e495ec63c3a73f9738ff51af0e70682cfe66e760 (HEAD -> master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 17:00:29 2023 +0530

    multipication

commit 2d3c492161307c23bde7c041825d8a381e6145bb
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)

git merge
-----------
rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (master)
$ git checkout -b division
Switched to a new branch 'division'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ ls
1.sh  devops/

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ vi 1.sh

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ git status
On branch division
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   1.sh

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   1.sh


rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ git add .

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ git commit -m "adding division functionality"
[division 19c6df2] adding division functionality
 1 file changed, 2 insertions(+)

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)
$ git log
commit 19c6df2c71b649a5509323b5b72f38e43b491223 (HEAD -> division)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 17:19:33 2023 +0530

    adding division functionality

commit e495ec63c3a73f9738ff51af0e70682cfe66e760 (master)
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 17:00:29 2023 +0530

    multipication

commit 2d3c492161307c23bde7c041825d8a381e6145bb
Author: ramakant <enginer.chintu@gmail.com>
Date:   Fri May 26 15:50:41 2023 +0530

    this is my first version'

rathram@VQFQADTKPM MINGW64 ~/Desktop/Devops (division)

```
![image](https://github.com/rkrath123/devops/assets/53966749/fbea2cb4-5626-4ec2-acd2-7c73bdae0a66)
