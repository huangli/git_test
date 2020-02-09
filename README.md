# Pro Git 测试记录

# T1: 创建远程分支test
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

