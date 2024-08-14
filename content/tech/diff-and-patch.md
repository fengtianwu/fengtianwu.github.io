+++
title = 'Diff and Patch'
date = 2024-08-08T08:32:12+08:00
draft = false
+++

1. create patch file using diff or git diff

```
$ diff -u old new > old.patch
$ git diff commit-id old > old.patch

```

2. patch old

```
$ patch old old.patch 
```

3. git archive
```
$ git archive HEAD -o a.tar.gz
```