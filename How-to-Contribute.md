# 如何参与贡献

本项目使用 `markdown` + `docsify` + `GitHub Pages` 部署

!> docsify 扩展 markdown 的[新语法](https://docsify.js.org/#/zh-cn/helpers)，有部分新加入的语法

首先需要确保本地有 [Node.js](https://nodejs.org/en) 环境，且已经安装好了 [docsify](https://docsify.js.org/#/zh-cn/quickstart) 依赖，将项目 fork 到自己仓库后 clone 到本地，创建新分支进行修改，修改完成后 push 到远程仓库，然后向本仓库提起 PR 即可

!> 注意，为了避免一些莫名其妙的错误，请勿使用相对路径，在使用时请使用从 docs 开始的绝对路径`<br/>`例如: `docs/课内笔记/大一上/高等数学上/笔记/导数.md`

## 项目结构

```
├─docs
│  ├─升学&出国
|      ├─考研
|      ├─保研
|      ├─工作
|      └─出国
│  ├─学长学姐有话说
│  └─课内笔记
│      ├─大一上
|          ├─README.md                  -->     当前年级课程目录列表
|          ├─高等数学上                  -->      科目目录
|              ├─README.md              -->     科目介绍
|              ├─_sidebar.md            -->     进入当前科目时的侧边栏
|              ├─.nojekyll              -->     空文件，提示 GitHub 不要忽视_开头的文件
|              ├─笔记                   -->     笔记目录
|                 └─notes...
|              └─考试经验帖.md           -->     学长学姐经验总结
|          └─...
│      ├─大一下
│      ├─ ....
│      ├─大四上
│      └─实训&实验
├─README.md
├─_navbar.md
├─_sidebar.md
├─_converpage.md
├─How to contribute
├─.nojekyll
└─脚本
```

## 课内笔记部分

> 目前大三下/编译原理有内容，可以参考一下

### 添加新科目

添加新科目时需要按照固定的文档结构添加，以确保可以被 docsify 正常解析到，在添加新科目时，请在对应学期内创建科目文件夹，并创建 `README.md`, `_siderbar.md`, `.nojekyll`, `考试经验帖.md`四个基础文件以及 `笔记`文件夹，并在 `README.md`添加对应的学科介绍

`_siderbar.md`中的基础内容如下(以高等数学为参考, 添加后请修改到对应的目录下):

```markdown
-   [课程介绍](docs/课内笔记/大一上/高等数学上/README.md)
-   [考试经验帖](docs/课内笔记/大一上/高等数学上/考试经验帖.md)
-   笔记
    -   [导数](docs/课内笔记/大一上/高等数学上/笔记/导数.md)
```

在当前目录创建完成之后，还需要在 `docs/课内笔记/README.md`及 `docs/课内笔记/学期/README.md`中添加对应的科目信息，均指向当前科目的 `README.md`文件

做完基础的配置之后，就可以添加自己的笔记文件到对应科目笔记目录下, 添加完成后，记得在当前科目 `_sidebar.md`中添加对应的笔记条目以确保侧边栏可以正常显示该笔记条目

### 上传笔记

如果你需要添加的科目已经有了对应的文件夹，那么你只需要将自己的笔记文件上传到对应科目的笔记目录中(新建一个自己名字命名的文件夹)，并在 `科目名/README.md`中添加自己的笔记信息确保可以在侧边栏显示

### 补充考试经验帖

所有的考试经验帖均放在一个 markdown 文件中维护，因此每个人需使用二级标题对自己的内容进行划分，使用三级或四级标题对自己的内容划分，例如：

```md
## 张三

太难啦太难啦，不会呀

### 复习建议

好好复习好好复习好好复习

### 复习计划

好好复习好好复习好好复习
```

## 升学&就业部分

!> 对于有些部分可能会要求使用自己的**姓名**，如果你不想透漏个人信息的话，用**匿名昵称**也可以。<br/>
对于联系方式也如此，可以留**邮箱，QQ，微信**之类的，留联系方式主要是为了学弟学妹们联系方便，如果不想被打扰，在对应栏目中填入 `-`即可

该部分每人通过单独的 `markdown` 文件分享自己的经验，文档内部格式自由组织，将 `markdown` 文件统一存储在对应目录下的经验帖中，起名设置为`姓名+考研(保研/工作/出国)+经验帖.md`，文件创建完成后需要在当前目录的`_sidebar.md`和`README.md`文件中添加对应条目，然后在`docs/升学&就业/README.md`中也添加对应条目即可

## 分流&转专业部分

该部分文件存储位置在`docs/分流&转专业`文件夹中， 其中又分为分流和转专业两个子文件夹，可以根据自己的情况将内容放入对应的文件夹中，命名格式为`姓名+分流/转专业+经验帖.md`，文件创建完成后需要在当前目录的`_sidebar.md`和`README.md`文件中添加对应条目即可



## 学长学姐有话说部分

类似于升学&就业部分，也是通过每个人单独一个 `markdown`文件进行维护，将文件存储在对应目录下的经验帖目录中，文件名设置为 `姓名.md`，文件创建完毕后需要在 `docs/学长学姐有话说/经验帖/_sidebar.md`和 `docs/学长学姐有话说/README.md`中添加对应的条目

## 如何添加 PDF 文件预览

!> 注意：由于 GitHub 限制每个仓库的大小为 500MB，为了确保仓库容量，请在自己的 GitHub 创建一个单独的 repository，然后将 PDF 文件传到自己的仓库中，最后在刚刚创建的 md 文件中按照下面的格式要求写入预览 PDF 的链接即可<br/>
另外，尽量在上传前对自己的 PDF 文件进行**压缩**，减少文件大小，加快响应时间，可使用 [I love pdf](https://www.ilovepdf.com/zh-cn/compress_pdf) 网站进行压缩

在添加 PDF 文件时候，需要先创建一个对应的 markdown 文件，在文件中按照下面的格式书写即可链接到 PDF 文件

````txt
```pdf
 path to the pdf file
```

````

例如, 我想在 `docs/课内笔记/大一上/高等数学上/笔记/导数.md`中引用一个 PDF, 我只需要在 `导数.md`中写入下面的内容即可:

````txt
```pdf
预览pdf的url
```
````