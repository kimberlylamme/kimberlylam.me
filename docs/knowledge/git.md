---
title: Git命令
last_update:
  date: 2022-08-10
---

### 设置账号邮箱

```shell
$ git config --list --show-origin
$ git config --global user.name "Kimberly"
$ git config --global user.email kimberly@example.com
```

### 创建一个新存储库

```shell
$ git init
$ git add README.md
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin git@github.com:kimberlylamme/projects.git
$ git push -u origin main
```

### 推送现有存储库

```shell
$ git remote add origin git@github.com:kimberlylamme/projects.git
$ git branch -M main
$ git add .
$ git commit -m "frist commit"
$ git push -u origin main
```

### 克隆远程存储库

```shell
$ git clone git@github.com:kimberlylamme/projects.git
```

### 分支管理

```shell
$ git branch
$ git branch dev
$ git checkout dev
#分支提交
$ git add test.txt
$ git commit -m "branch test"
$ git push origin dev
#合并分支
$ git checkout main
$ git merge dev
#删除分支
$ git branch -d dev
```

### 创建补丁

```shell
#patch补丁
$ git format-patch [sha1 id]..[sha1 id]
#diff补丁
$ git diff [sha1 id] [sha1 id] > patch.diff
#检查patch/diff是否能正常打入
$ git apply --check patch.diff
#打入补丁
$ git apply patch.diff
#强制打入补丁
$ git apply --reject patch.diff
```

