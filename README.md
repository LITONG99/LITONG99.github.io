# Tong Li 的学术主页

主页采用 [academic-homepage](https://github.com/luost26/academic-homepage) 的 Jekyll 双栏模板。模板源版本为 `69f6589`，MIT 许可证位于 `docs/LICENSE`。

## 在 VS Code Remote SSH 预览

在远程终端运行：

```bash
cd /hpc2hdd/home/tlice/myprojects/homepage/docs
bundle install
bundle exec jekyll serve --host 127.0.0.1 --port 8001
```

如果当前服务器的终端找不到 `bundle`，先运行 `conda activate "$HOME/.cache/tong-homepage-ruby"`，再执行上面的命令。

在 VS Code 的 **端口（Ports）** 面板转发 `8001`，点击 **在浏览器中打开**。保持远程终端运行。修改后刷新浏览器，修改 `_config.yml` 后重启 Jekyll。

也可以用 Python 预览已经构建的静态文件：

```bash
cd /hpc2hdd/home/tlice/myprojects/homepage
python3 -m http.server 8001 --bind 127.0.0.1 --directory docs/_site
```

## 在 GitHub Pages 发布

1. 将项目提交到 `<用户名>.github.io` 仓库的 `main` 分支。
2. 在仓库的 **Settings → Pages** 选择 **Deploy from a branch**，分支选 `main`，目录选 `/docs`。
3. 如果使用普通项目仓库，将 `docs/_config.yml` 中的 `baseurl` 改为 `/<仓库名>`。

[GitHub Pages 发布源配置文档](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## 更新内容

- 简介、学校邮箱、教育、实习和审稿服务在 `docs/_data/profile.yml`。
- 每篇论文对应 `docs/_publications/` 下的一个文件。`selected: true` 将论文展示在首页。可以用 `links` 添加论文链接，用 `cover` 指定配图。
- 头像在 `docs/assets/portrait.jpg`。
- `materials/` 存放原始简历，已加入 Git 忽略列表。
