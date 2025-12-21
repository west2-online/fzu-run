# 贡献指南

## 转专业文章
### 编写规范
我们没有强制规范，你可以参照其他人所写的文章  
但是请使用 markdown 语法，你可以在这里查看[Markdown 教程](https://markdown.com.cn)  
对于换段，请使用两次换行，也就是使用一个空行隔开；如果你想使用普通的换行，请在上一行结尾添加两个空格再进行一次换行即可  
注意标点符号的使用，参见[中文标点符号规范](https://github.com/itheima2017/markdown-doc/blob/master/2.%E4%B8%AD%E6%96%87%E5%86%99%E4%BD%9C%E8%A7%84%E8%8C%83/2.5-%E6%A0%87%E7%82%B9%E7%AC%A6%E5%8F%B7.md)，并且不要混用中英文符号    
如果你需要引用本网站上的另一篇文章，请使用相对目录语法，也就是另一篇文章的 md 文件相对于你的文章 md 的路径，
比如你需要在转专业文章中引用备考资源，使用`[2022计算机机试题目](../source/2022-cs-on-computer-exam.md)`
对于一些扩展语法，比如文字颜色或者 $\rm\LaTeX$，可以自行查询 mkdocs 是否提供了相应支持，并且在本地部署 mkdocs 环境进行调试  
如果不知道怎么做，你也可以创建一个 issues 来询问  

### 上传规范

将你编写的 markdown 文件放置于 `/docs/change-major/{转入学科}` 下

如果你没有找到对应学科的目录，也可以自行创建

文档的命名遵循以下规则：

    {年份}{月份}{日期}-{编号}.md

    其中年份取低两位（我们认为文档是不会一直到 2100 年还在使用的）
    月份和日期不到两位的，在高位上补0
    编号按照同一日内的文章上传顺序依次顺延

放置好 markdown 文件后，你需要修改 `mkdocs.yml` 来让别人可以看到你的文章

在 `nav > 转专业 > {转入学科}` 下添加你的文章
名字遵循以下规则：
`[{年级}]{转专业年份}-{原专业}->{现专业}`
同样的，如果你没有找到对应学科，也可以自行增加

注意，请不要在两个不同分支上分开进行文章的添加和`mkdocs.yml`的修改，再为每个分支创建两个 pr，如果你不知道这句话在说什么，请考虑询问 AI 以了解 git 基础知识  
我们推荐的流程是：创建本仓库 fork -> 从自己 fork 的仓库的 main 创建一个新的临时分支进行提交 -> 使用这个临时分支创建 pr -> 等待 pr 通过后该临时分支即可删除 -> 自己 fork 的仓库的 main 分支拉取原仓库的最新更改

**注意：请不要使用一级标题（#），第一级标题从二级标题（##）开始**

## 研究生文章
### 编写规范
同样不设定强制规范，请随意决定文章的格式

### 上传规范
与转专业文章大体相同

markdown 文件放置在 `/docs/postgraduate/{学校}` 下

`.md` 文件命名规范与转专业文章相同

在 `nav > 研究生 > {学校}` 下添加你的文章

名字遵循以下规则：
`[考研/保研] {年级}-{学院/专业方向}`

## 添加图片
如果你想在文章中添加图片，可以自行选择图床并在文章中插入链接

或者也可以联系我们，我们会将你的图片上传至我们的图床后提供对应的链接

## 预览文章
此项是非必需的，但是我们**强烈建议**你在上传文件前进行预览，以便确认文章的展示效果。

本项目采用 [Mkdocs](https://www.mkdocs.org/) 及其对应主题 [Mkdocs-Material](https://squidfunk.github.io/mkdocs-material/)，您可以自行参考官网或第三方教程安装，我们这里也提供 python 安装方式

你需要先安装 `python`

**[选做]**:创建虚拟环境

```
python3 -m venv mkdocs_venv
# 激活虚拟环境
mkdocs_venv\Scripts\activate # Windows
source mkdocs_venv/bin/activate # Unix 或 MacOS
```

随后运行以下命令
```
pip install mkdocs
pip install mkdocs-material
pip install mkdocs-glightbox
pip install mkdocs-git-revision-date-localized-plugin
```
如果你发现安装极为缓慢甚至安装失败，请参阅 [PyPI 镜像使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)

安装完成后，在项目目录下运行 `mkdocs serve`
访问 http://127.0.0.1:8000 即可预览你的文章
