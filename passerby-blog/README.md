# 「不起眼的路过」部署指南（GitHub Pages）

这套源码是一个可直接部署到 GitHub Pages 的个人主页品牌站。你只需要**全程在网页上点鼠标**，不需要安装任何东西。

---

## 一、注册 GitHub（如果还没有账号）

1. 打开 https://github.com ，点 **Sign up**
2. 填邮箱、设密码、起个用户名，按提示完成验证
3. 注册免费，不需要付费

记下你的**用户名**（username），后面要用。

---

## 二、创建一个仓库（Repository）

1. 登录后，点右上角 **+** → **New repository**
2. **Repository name** 填：**`你的用户名.github.io`**
   （例如用户名是 `weng`，就填 `weng.github.io`）
3. 选 **Public**（公开，别人才能看）
4. 先不要勾选任何初始化选项，直接点底部 **Create repository**

---

## 三、把网站源码上传进去

1. 在刚建好的仓库页面，点 **Add file** → **Upload files**
2. 找到本机文件夹 `passerby-blog`，**打开它**，把里面的**所有文件和文件夹**（`_config.yml`、`_layouts`、`_includes`、`_posts`、`assets`、`index.html`、`works.md`、`about.md`、`blog.html`、`_data`）**全部拖进网页的虚线框**
3. 往下拉，直接点 **Commit changes**

> 注意：不要只拖 `passerby-blog` 这个文件夹本身，要拖它**里面的内容**，这样文件才会落在仓库根目录。

---

## 四、开启 GitHub Pages

1. 在仓库页面点 **Settings**（设置）
2. 左侧菜单点 **Pages**
3. 在 **Build and deployment** 的 **Source** 下拉选 **Deploy from a branch**
4. **Branch** 选 **main**，右侧目录选 **/(root)**，点 **Save**
5. 等待约 1–2 分钟，页面顶部会出现你的网址：**`https://你的用户名.github.io/`**

打开这个网址，你的「不起眼的路过」就上线了，全公网可访问。

---

## 五、之后怎么更新

### 写一篇新随笔（核心）
1. 进仓库，打开 `_posts` 文件夹 → **Add file** → **Create new file**
2. **文件名**写：`2026-11-01-标题.md`（格式必须是 `年-月-日-标题.md`）
3. 在编辑框里填：

```markdown
---
layout: post
title: 文章标题
date: 2026-11-01
tags: [随笔]
---
正文写在这里，支持 Markdown 格式。
```

4. 点 **Commit changes**。约 1 分钟内网站自动更新，新文章公开。

### 加一个作品
1. 打开 `_data/works.yml`
2. 照下面的格式在末尾加一段：

```yaml
- title: 作品名称
  desc: 一两句介绍
  link: https://作品链接
  status: 已完成
```

3. 不想放链接就把 `link:` 留空。**Commit changes** 即可。

### 改个人介绍
打开根目录的 `about.md`，改文字后 **Commit changes**。

---

## 六、如果网址打开样式乱或图片不显示

在仓库根目录打开 `_config.yml`，把这两行改掉再提交：

```yaml
url: ""            # 改成 https://你的用户名.github.io
baseurl: ""        # 如果你仓库名就叫「用户名.github.io」，保持空即可
```

---

## 七、常见问题

- **打开是 404**：可能 Pages 还在构建，等 2 分钟刷新；或仓库名拼写和用户名不一致。
- **想用自己的域名**：GitHub Pages 支持自定义域名（需自己购买，可选）。
- **国内访问偶尔慢**：GitHub Pages 服务器在国外，一般能用，偶尔稍慢；可后续考虑加 CDN。

这套站也可以随时交给我，我帮你改结构、换风格、批量加内容。
