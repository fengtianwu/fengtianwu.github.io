+++
title = '用hugo写blog'
date = 2024-08-05T13:44:13+08:00
draft = false
+++

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

6. 贴一篇博文, 并推到github上
```
hugo new content content/posts/用hugo写blog.md

vi content/posts/用hugo写blog.md

git add content/posts/用hugo写blog.md
git commit
git push
```

