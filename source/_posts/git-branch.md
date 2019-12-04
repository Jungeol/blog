---
title: git-branch
tag: git
category: git
date: 2019-12-04 21:40:29
---
# branch
## create branch
```
$ git branch {{branch-name}}
```
see branch info -> log with decorate option.
```
$ git log --decorate
```
## switch to branch
```
$ git checkout {{branch-name}}
```
with create branch: -b option
## merge
```
$ git checkout {{master-branch}}
$ git merge {{branch-name}}
```
## delete branch
when merged well, delete branch
```
$ git branch -d {{branch-name}}
```
