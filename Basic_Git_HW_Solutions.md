# test

#Question 1

(base) devins-mbp:~ devinfagan$ cd Desktop/
 
(base) devins-mbp:Desktop devinfagan$ mkdir test
(base) devins-mbp:Desktop devinfagan$ tree test
test

0 directories, 0 files
(base) devins-mbp:Desktop devinfagan$ cd test

(base) devins-mbp:test devinfagan$ git init
Initialized empty Git repository in /Users/devinfagan/Desktop/test/.git/

  (base) devins-mbp:test devinfagan$ git add a.txt

(base) devins-mbp:test devinfagan$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

new file:   a.txt

(base) devins-mbp:test devinfagan$ git commit
[master (root-commit) dae3679] "a.txt"
1 file changed, 1 insertion(+)
create mode 100644 a.txt

(base) devins-mbp:test devinfagan$ git status
On branch master
nothing to commit, working tree clean

#Question 2
(base) devins-mbp:test devinfagan$ mkdir subtest
(base) devins-mbp:test devinfagan$ pwd
/Users/devinfagan/Desktop/test
(base) devins-mbp:test devinfagan$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

subtest/
  
  nothing added to commit but untracked files present (use "git add" to track)
(base) devins-mbp:test devinfagan$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

a1.txt
b1.txt
subtest/
  
  nothing added to commit but untracked files present (use "git add" to track)
(base) devins-mbp:test devinfagan$ git add .
(base) devins-mbp:test devinfagan$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

new file:   a1.txt
new file:   b1.txt
new file:   subtest/b.txt

(base) devins-mbp:test devinfagan$ git commit -m "all of em"
[master 26fb332] all of em
3 files changed, 3 insertions(+)
create mode 100644 a1.txt
create mode 100644 b1.txt
create mode 100644 subtest/b.txt

(base) devins-mbp:test devinfagan$ git log --oneline
26fb332 (HEAD -> master) all of em
dae3679 "a.txt"

#Question 3
devins-mbp:test devinfagan$ git remote add test https://github.com/DevinFagan/test.git

(base) devins-mbp:test devinfagan$ git remote -v
test	https://github.com/DevinFagan/test.git (fetch)
test	https://github.com/DevinFagan/test.git (push)
(base) devins-mbp:test devinfagan$ git add .

(base) devins-mbp:test devinfagan$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

modified:   a.txt

(base) devins-mbp:test devinfagan$ git diff --staged
diff --git a/a.txt b/a.txt
index ab0fd0f..aa48e9c 100644
--- a/a.txt
+++ b/a.txt
@@ -1 +1,2 @@
  -Git is good
\ No newline at end of file
+Git is good
+Github is awesome
\ No newline at end of file

(base) devins-mbp:test devinfagan$ git commit -m "newline"
[master fc3edc4] newline
1 file changed, 2 insertions(+), 1 deletion(-)

(base) devins-mbp:test devinfagan$ git push -u test master
Counting objects: 12, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (12/12), 934 bytes | 467.00 KiB/s, done.
Total 12 (delta 0), reused 0 (delta 0)
To https://github.com/DevinFagan/test.git
* [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'test'.

#Question 4
devins-mbp:test devinfagan$ git log --oneline
fc3edc4 (HEAD -> master, test/master) newline
26fb332 all of em
dae3679 "a.txt"

(base) devins-mbp:test devinfagan$ git checkout 26fb332
Note: checking out '26fb332'.


  HEAD is now at 26fb332... all of em
(base) devins-mbp:test devinfagan$ git reset 26fb332

  (base) devins-mbp:test devinfagan$ git status
HEAD detached at 26fb332
nothing to commit, working tree clean

(base) devins-mbp:test devinfagan$ git log --oneline
26fb332 (HEAD) all of em
dae3679 "a.txt"

(base) devins-mbp:test devinfagan$ git reset dae3679

(base) devins-mbp:test devinfagan$ git log --oneline
dae3679 (HEAD) "a.txt"

(base) devins-mbp:test devinfagan$ git add .

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

new file:   a1.txt
new file:   b1.txt
new file:   subtest/b.txt

(base) devins-mbp:test devinfagan$ git commit -m "all of them"
[detached HEAD 04652ca] all of them
3 files changed, 3 insertions(+)
create mode 100644 a1.txt
create mode 100644 b1.txt
create mode 100644 subtest/b.txt

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

modified:   a1.txt

no changes added to commit (use "git add" and/or "git commit -a")

(base) devins-mbp:test devinfagan$ git log --oneline
04652ca (HEAD) all of them
dae3679 "a.txt"

(base) devins-mbp:test devinfagan$ git add a1.txt

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

modified:   a1.txt

(base) devins-mbp:test devinfagan$ git reset --hard
HEAD is now at 04652ca all of them

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
nothing to commit, working tree clean

(base) devins-mbp:test devinfagan$ git log --oneline
04652ca (HEAD) all of them
dae3679 "a.txt"

(base) devins-mbp:test devinfagan$ git add al.text
fatal: pathspec 'al.text' did not match any files

(base) devins-mbp:test devinfagan$ git add .

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

modified:   a1.txt

(base) devins-mbp:test devinfagan$ git commit -m a1.text
[detached HEAD e2bdf89] a1.text
1 file changed, 2 insertions(+), 1 deletion(-)

(base) devins-mbp:test devinfagan$ git reset

(base) devins-mbp:test devinfagan$ git status
HEAD detached from 26fb332
nothing to commit, working tree clean

(base) devins-mbp:test devinfagan$ git log
commit e2bdf8909b7f13b5148e5a0e34a5ec9c30c07b5d (HEAD)
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 18:36:12 2020 -0400

a1.text

commit 04652ca9c6523738c03fa185e64b124949948021
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 18:20:12 2020 -0400

all of them

commit dae36799b4ec3771dfd370ea84e87b706d039b9d
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 16:46:54 2020 -0400

"a.txt"
(base) devins-mbp:test devinfagan$ git reset --hard
HEAD is now at e2bdf89 a1.text

(base) devins-mbp:test devinfagan$ git log
commit e2bdf8909b7f13b5148e5a0e34a5ec9c30c07b5d (HEAD)
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 18:36:12 2020 -0400

a1.text

commit 04652ca9c6523738c03fa185e64b124949948021
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 18:20:12 2020 -0400

all of them

commit dae36799b4ec3771dfd370ea84e87b706d039b9d
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 16:46:54 2020 -0400

"a.txt"

(base) devins-mbp:test devinfagan$ git log --oneline
e2bdf89 (HEAD) a1.text
04652ca all of them
dae3679 "a.txt"

(base) devins-mbp:test devinfagan$ git checkout e2bdf89
HEAD is now at e2bdf89... a1.text

(base) devins-mbp:test devinfagan$ git checkout 04652ca

HEAD is now at 04652ca... all of them

(base) devins-mbp:test devinfagan$ git reset 04652ca

(base) devins-mbp:test devinfagan$ git log
commit 04652ca9c6523738c03fa185e64b124949948021 (HEAD)
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 18:20:12 2020 -0400

all of them

commit dae36799b4ec3771dfd370ea84e87b706d039b9d
Author: Devin Fagan <devinfagan38@gmail.com>
  Date:   Wed Apr 8 16:46:54 2020 -0400

"a.txt"


