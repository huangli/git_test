# Pro Git 测试记录

个人学习《Pro Git》的测试，github 上创建了一个git_test 的仓库。有些命令是用的缩写，参照[oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet#git)。

# Test 001: 创建远程分支test
```terminal
# 本地创建分支test
$ gcb test

# 创建1.py文件并且commit
$ touch 1.py
$ ga .
$ gc -m "initial commit"

# remote 创建了一个test branch
$ git push origin test
```

# Test 002: 本地Merge branch
```terminal
# 此时 master 和test branch 因为添加了Test002已经不同
# check out to master
$ gcm
# 合并test
$ git merge test
# git push origin master
$ ggp
```

# Test 003: 删除远程分支
```terminal
$ gcm
# 创建新的分支
$ gcb test_delete

# push 到repository
$ git push origin test_delete
Connection to github.com 22 port [tcp/ssh] succeeded!
To github.com:huangli/git_test.git
 - [deleted]         test_delete

# 删除本地分支
$ git branch -d test_delete
Deleted branch test_delete (was faa28e2).
```

# Test 004: 删除本地分支， 再从远程下载
```terminal
# 此时有两个branch, test 和 master
$ gco test
$ git branch -D master
Deleted branch master (was 20df121).

# 下载，此时pull 和 fetch 都可以
$ git pull origin master 
$ git fetch origin master
# 切换到master
$ gcm
# 此时有master 了
# git branch 
* master
test
```

# Test 005: Alias 懒人提交

```bash
# github上的博客通过一个命令提交，而不是每次都三个命令，反正只有一个master branch
alias blog="git add . && git commit -m $(date +%Y-%m-%d) && ggp" 
```