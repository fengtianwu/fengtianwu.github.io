+++
title = '用hugo写blog'
date = 2024-08-05T13:44:13+08:00
draft = false
+++

# 在本地计算机上

1. 安装hugo
```
brew install hugo
hugo version
```

2. 新建一个场子

```
hugo new site fengtianwu.github.io
```

3. 克隆一个主题 

```
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```


4. 配置文件中添加主题

```
echo "theme = 'ananke'" >> hugo.toml
```

5. 启动服务器, 并根据提示在本地浏览

```
hugo server -D
```

6. 写一篇博文, 新建markdown文件, 并加上文件头.
```
hugo new content content/posts/用hugo写blog.md
```
文件头长这样:
```
+++
title = '用hugo写blog'
date = 2024-08-05T13:44:13+08:00
draft = true
+++

```
7. 如果要推到github上, 博文的头部draft的值改为false.
```
+++
title = '用hugo写blog'
date = 2024-08-05T13:44:13+08:00
draft = false
+++

```

# [搞到github上](https://gohugo.io/hosting-and-deployment/hosting-on-github/)


