+++

title = 'Blogging using Hugo'
date = 2024-08-05T13:44:13+08:00
draft = false
+++

# Development on local

1. install hugo
```
brew install hugo
hugo version
```

2. new site

```
hugo new site fengtianwu.github.io
```

3. clone a theme

```
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
```


4. Add a new theme in the configuration file named hugo.toml

```
echo "theme = 'ananke'" >> hugo.toml
```

5. start server

```
hugo server -D
```

6. new content at posts dir
```
hugo new content content/posts/Blogging\ using\ Hugo.md
```

  file header looks like this:

```
+++
title = 'Blogging using Hugo'
date = 2024-08-05T13:44:13+08:00
draft = true
+++
```

7. To publish to github, the value of **draft** must be **false**.

```
+++
title = 'Blogging using Hugo'
date = 2024-08-05T13:44:13+08:00
draft = false
+++

```

# [Host on GitHub Pages](https://gohugo.io/hosting-and-deployment/hosting-on-github/)


