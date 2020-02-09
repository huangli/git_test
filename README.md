# Pro Git 测试记录

个人学习《Pro Git》的测试，github 上创建了一个git_test 的仓库。有些命令不是完整的，[oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet#git)是上的缩写。

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
$ gcb test_delete
$ git push origin test_delete
$ git push origin --delete test_delete
```