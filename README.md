这个是我第一次使用git 完成win上的操作， 然后所有操作内容和讲解都在语阙git win 和git win2上面。
这个是实际的代码。 



lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git --version
git version 2.47.1.windows.1

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git confit --list
git: 'confit' is not a git command. See 'git --help'.

The most similar command is
        config

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=E:/Git/mingw64/etc/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git config --global user.name "YueYang"

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git config --global user.email "loveyueyang@gmail.com"

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=E:/Git/mingw64/etc/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.name=YueYang
user.email=loveyueyang@gmail.com

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1
$ git init
Initialized empty Git repository in F:/GitRepository/gitRepo1/.git/

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo1.txt
fatal: pathspec 'demo1.txt' did not match any files

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "这是我上传的第一个文件demo1.txt" demo1.txt
[master (root-commit) 7d0c9fc] 这是我上传的第一个文件demo1.txt
 1 file changed, 1 insertion(+)
 create mode 100644 demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        demo2.txt

nothing added to commit but untracked files present (use "git add" to track)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo2.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   demo2.txt


lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ^C

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "我提交了demo2.txt测试文件，测试上传状态" demo2.txt
[master 1b924af] 我提交了demo2.txt测试文件，测试上传状态
 1 file changed, 1 insertion(+)
 create mode 100644 demo2.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo.txt
cat: demo.txt: No such file or directory

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo1.txt
这是我第一个上传仓库的操作文件
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo2.txt
测试我不上传，使用git status命令会不会提示我没有上传这个文件。
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git log
commit 1b924afc1303a74e31e540f0db60692aa88712c3 (HEAD -> master)
Author: YueYang <loveyueyang@gmail.com>
Date:   Tue Jan 14 10:47:17 2025 +0800

    我提交了demo2.txt测试文件，测试上传状态

commit 7d0c9fca560e3f6a193d770248e06db46597e3cd
Author: YueYang <loveyueyang@gmail.com>
Date:   Tue Jan 14 10:24:08 2025 +0800

    这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
1b924af (HEAD -> master) HEAD@{0}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{1}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   demo2.txt

no changes added to commit (use "git add" and/or "git commit -a")

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo2.txt
测试我不上传，使用git status命令会不会提示我没有上传这个文件。
测试demo2的版本回溯功能，这一行是我版本2添加的内容。
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo2.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   demo2.txt


lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "这是修改过demo2文件重新提交记录" demo2.txt
[master 8751dde] 这是修改过demo2文件重新提交记录
 1 file changed, 2 insertions(+), 1 deletion(-)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
8751dde (HEAD -> master) HEAD@{0}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{1}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{2}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reset --hard 1b924af
HEAD is now at 1b924af 我提交了demo2.txt测试文件，测试上传状态

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
1b924af (HEAD -> master) HEAD@{0}: reset: moving to 1b924af
8751dde HEAD@{1}: commit: 这是修改过demo2文件重新提交记录
1b924af (HEAD -> master) HEAD@{2}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{3}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo2.txt
测试我不上传，使用git status命令会不会提示我没有上传这个文件。
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
1b924af (HEAD -> master) HEAD@{0}: reset: moving to 1b924af
8751dde HEAD@{1}: commit: 这是修改过demo2文件重新提交记录
1b924af (HEAD -> master) HEAD@{2}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{3}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reset --hard 8751dde
HEAD is now at 8751dde 这是修改过demo2文件重新提交记录

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo2.txt
测试我不上传，使用git status命令会不会提示我没有上传这个文件。
测试demo2的版本回溯功能，这一行是我版本2添加的内容。
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
8751dde (HEAD -> master) HEAD@{0}: reset: moving to 8751dde
1b924af HEAD@{1}: reset: moving to 1b924af
8751dde (HEAD -> master) HEAD@{2}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{3}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{4}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        demo3.txt

nothing added to commit but untracked files present (use "git add" to track)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo3.txt
测试我要删除的文件 demo3.txt
lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo3.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "删除demo3文件上传" demo3.txt
[master 16702ac] 删除demo3文件上传
 1 file changed, 1 insertion(+)
 create mode 100644 demo3.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
16702ac (HEAD -> master) HEAD@{0}: commit: 删除demo3文件上传
8751dde HEAD@{1}: reset: moving to 8751dde
1b924af HEAD@{2}: reset: moving to 1b924af
8751dde HEAD@{3}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{4}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{5}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ rm demo3.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
16702ac (HEAD -> master) HEAD@{0}: commit: 删除demo3文件上传
8751dde HEAD@{1}: reset: moving to 8751dde
1b924af HEAD@{2}: reset: moving to 1b924af
8751dde HEAD@{3}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{4}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{5}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ cat demo3.txt
cat: demo3.txt: No such file or directory

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo3.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        deleted:    demo3.txt


lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "删除demo3文件的提交操作" demo3.txt
[master 7ef863e] 删除demo3文件的提交操作
 1 file changed, 1 deletion(-)
 delete mode 100644 demo3.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
7ef863e (HEAD -> master) HEAD@{0}: commit: 删除demo3文件的提交操作
16702ac HEAD@{1}: commit: 删除demo3文件上传
8751dde HEAD@{2}: reset: moving to 8751dde
1b924af HEAD@{3}: reset: moving to 1b924af
8751dde HEAD@{4}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{5}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{6}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reset --hard 16702ac
HEAD is now at 16702ac 删除demo3文件上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
16702ac (HEAD -> master) HEAD@{0}: reset: moving to 16702ac
7ef863e HEAD@{1}: commit: 删除demo3文件的提交操作
16702ac (HEAD -> master) HEAD@{2}: commit: 删除demo3文件上传
8751dde HEAD@{3}: reset: moving to 8751dde
1b924af HEAD@{4}: reset: moving to 1b924af
8751dde HEAD@{5}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{6}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{7}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        demo4.txt

nothing added to commit but untracked files present (use "git add" to track)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo4.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m"这是测试差异的demo4文件" demo4.txt
[master f1e2dc6] 这是测试差异的demo4文件
 1 file changed, 1 insertion(+)
 create mode 100644 demo4.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   demo4.txt

no changes added to commit (use "git add" and/or "git commit -a")

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git diff demo4.txt
diff --git a/demo4.txt b/demo4.txt
index af6f6d5..f6d2402 100644
--- a/demo4.txt
+++ b/demo4.txt
@@ -1 +1,2 @@
-这是demo4文件原有的内容
\ No newline at end of file
+这是demo4文件原有的内容
+这一行是demo4添加的内容。
\ No newline at end of file

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo4.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m"demo4修改冲内容重新上传" demo4.txt
[master 1d16409] demo4修改冲内容重新上传
 1 file changed, 2 insertions(+), 1 deletion(-)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
1d16409 (HEAD -> master) HEAD@{0}: commit: demo4修改冲内容重新上传
f1e2dc6 HEAD@{1}: commit: 这是测试差异的demo4文件
16702ac HEAD@{2}: reset: moving to 16702ac
7ef863e HEAD@{3}: commit: 删除demo3文件的提交操作
16702ac HEAD@{4}: commit: 删除demo3文件上传
8751dde HEAD@{5}: reset: moving to 8751dde
1b924af HEAD@{6}: reset: moving to 1b924af
8751dde HEAD@{7}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{8}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{9}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git branch -v
* master 1d16409 demo4修改冲内容重新上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git branch branch01

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git branch -v
  branch01 1d16409 demo4修改冲内容重新上传
* master   1d16409 demo4修改冲内容重新上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git checkout branch01
Switched to branch 'branch01'

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git branch -v
* branch01 1d16409 demo4修改冲内容重新上传
  master   1d16409 demo4修改冲内容重新上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git add demo5.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git commit -m"这是给branch01分支上上传的demo5文件" demo5.txt
[branch01 b6f6b6e] 这是给branch01分支上上传的demo5文件
 1 file changed, 1 insertion(+)
 create mode 100644 demo5.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git branch -v
* branch01 b6f6b6e 这是给branch01分支上上传的demo5文件
  master   1d16409 demo4修改冲内容重新上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git reflog
b6f6b6e (HEAD -> branch01) HEAD@{0}: commit: 这是给branch01分支上上传的demo5文件
1d16409 (master) HEAD@{1}: checkout: moving from master to branch01
1d16409 (master) HEAD@{2}: commit: demo4修改冲内容重新上传
f1e2dc6 HEAD@{3}: commit: 这是测试差异的demo4文件
16702ac HEAD@{4}: reset: moving to 16702ac
7ef863e HEAD@{5}: commit: 删除demo3文件的提交操作
16702ac HEAD@{6}: commit: 删除demo3文件上传
8751dde HEAD@{7}: reset: moving to 8751dde
1b924af HEAD@{8}: reset: moving to 1b924af
8751dde HEAD@{9}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{10}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{11}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (branch01)
$ git checkout master
Switched to branch 'master'

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git branch -v
  branch01 b6f6b6e 这是给branch01分支上上传的demo5文件
* master   1d16409 demo4修改冲内容重新上传

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git add demo5.txt
fatal: pathspec 'demo5.txt' did not match any files

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git commit -m "我要给master分支上上传demo5文件" demo5.txt
error: pathspec 'demo5.txt' did not match any file(s) known to git

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
1d16409 (HEAD -> master) HEAD@{0}: checkout: moving from branch01 to master
b6f6b6e (branch01) HEAD@{1}: commit: 这是给branch01分支上上传的demo5文件
1d16409 (HEAD -> master) HEAD@{2}: checkout: moving from master to branch01
1d16409 (HEAD -> master) HEAD@{3}: commit: demo4修改冲内容重新上传
f1e2dc6 HEAD@{4}: commit: 这是测试差异的demo4文件
16702ac HEAD@{5}: reset: moving to 16702ac
7ef863e HEAD@{6}: commit: 删除demo3文件的提交操作
16702ac HEAD@{7}: commit: 删除demo3文件上传
8751dde HEAD@{8}: reset: moving to 8751dde
1b924af HEAD@{9}: reset: moving to 1b924af
8751dde HEAD@{10}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{11}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{12}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git merge branch01
Updating 1d16409..b6f6b6e
Fast-forward
 demo5.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 demo5.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git reflog
b6f6b6e (HEAD -> master, branch01) HEAD@{0}: merge branch01: Fast-forward
1d16409 HEAD@{1}: checkout: moving from branch01 to master
b6f6b6e (HEAD -> master, branch01) HEAD@{2}: commit: 这是给branch01分支上上传的demo5文件
1d16409 HEAD@{3}: checkout: moving from master to branch01
1d16409 HEAD@{4}: commit: demo4修改冲内容重新上传
f1e2dc6 HEAD@{5}: commit: 这是测试差异的demo4文件
16702ac HEAD@{6}: reset: moving to 16702ac
7ef863e HEAD@{7}: commit: 删除demo3文件的提交操作
16702ac HEAD@{8}: commit: 删除demo3文件上传
8751dde HEAD@{9}: reset: moving to 8751dde
1b924af HEAD@{10}: reset: moving to 1b924af
8751dde HEAD@{11}: commit: 这是修改过demo2文件重新提交记录
1b924af HEAD@{12}: commit: 我提交了demo2.txt测试文件，测试上传状态
7d0c9fc HEAD@{13}: commit (initial): 这是我上传的第一个文件demo1.txt

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote -v

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote add origin https://github.com/YueYangOVO/TestGitCommand.git

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote -v
origin  https://github.com/YueYangOVO/TestGitCommand.git (fetch)
origin  https://github.com/YueYangOVO/TestGitCommand.git (push)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git status
On branch master
nothing to commit, working tree clean

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git push origin master
fatal: unable to access 'https://github.com/YueYangOVO/TestGitCommand.git/': OpenSSL SSL_read: SS
L_ERROR_SYSCALL, errno 0

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ^C

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git -v
git version 2.47.1.windows.1

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote -v
origin  https://github.com/YueYangOVO/TestGitCommand.git (fetch)
origin  https://github.com/YueYangOVO/TestGitCommand.git (push)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git push origin master
fatal: unable to access 'https://github.com/YueYangOVO/TestGitCommand.git/': OpenSSL SSL_read: SS
L_ERROR_SYSCALL, errno 0

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ^[[200~git remote set-url origin https://github.com/YueYangOVO/TestGitCommand.git~
bash: $'\E[200~git': command not found

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote set-url origin https://github.com/YueYangOVO/TestGitCommand.git

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git remote -v
origin  https://github.com/YueYangOVO/TestGitCommand.git (fetch)
origin  https://github.com/YueYangOVO/TestGitCommand.git (push)

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git push origin master
fatal: unable to access 'https://github.com/YueYangOVO/TestGitCommand.git/': Failed to connect to
 github.com port 443 after 21211 ms: Could not connect to server

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ curl -v https://github.com
* Host github.com:443 was resolved.
* IPv6: (none)
* IPv4: 20.205.243.166
*   Trying 20.205.243.166:443...
* schannel: disabled automatic use of client certificate
* schannel: failed to receive handshake, SSL/TLS connection failed
* closing connection #0
curl: (35) schannel: failed to receive handshake, SSL/TLS connection failed

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ pin
bash: pin: command not found

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ipipppp
bash: ipipppp: command not found

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ping github.com

正在 Ping github.com [20.205.243.166] 具有 32 字节的数据:
来自 20.205.243.166 的回复: 字节=32 时间=98ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=209ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=143ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=269ms TTL=113

20.205.243.166 的 Ping 统计信息:
    数据包: 已发送 = 4，已接收 = 4，丢失 = 0 (0% 丢失)，
往返行程的估计时间(以毫秒为单位):
    最短 = 98ms，最长 = 269ms，平均 = 179ms

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ping github.com

正在 Ping github.com [20.205.243.166] 具有 32 字节的数据:
来自 20.205.243.166 的回复: 字节=32 时间=109ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=98ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=121ms TTL=113
来自 20.205.243.166 的回复: 字节=32 时间=112ms TTL=113

20.205.243.166 的 Ping 统计信息:
    数据包: 已发送 = 4，已接收 = 4，丢失 = 0 (0% 丢失)，
往返行程的估计时间(以毫秒为单位):
    最短 = 98ms，最长 = 121ms，平均 = 110ms

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git push origin master
fatal: unable to access 'https://github.com/YueYangOVO/TestGitCommand.git/': Failed to connect to
 github.com port 443 after 21083 ms: Could not connect to server

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ ^C

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git config --global http.proxy

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git config --global http.proxy

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$ git push origin master
info: please complete authentication in your browser...
Enumerating objects: 21, done.
Counting objects: 100% (21/21), done.
Delta compression using up to 16 threads
Compressing objects: 100% (17/17), done.
Writing objects: 100% (21/21), 2.17 KiB | 555.00 KiB/s, done.
Total 21 (delta 5), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (5/5), done.
To https://github.com/YueYangOVO/TestGitCommand.git
 * [new branch]      master -> master

lyy30@DESKTOP-57DOJSG MINGW64 /f/GitRepository/gitRepo1 (master)
$
