# 如何开始一个新 amWiki 轻文库

## 开始一个新文库的步骤

>  [Atom](https://atom.io/ "打开Atom官网")开发参考[amwiki官网](http://amwiki.org/doc)，以下为 Node.js开发（推荐）。

1. ##### 事先准备：下载 Node.js (Javascript v8 引擎运行环境)，并安装

2. ##### 确保 node.js 安装成功：打开终端或命令行，通过命令 npm -v 检查有版本号提示

3. ##### 通过命令 npm install -g amwiki 安装项目
(注意：①必须带全局参数 '-g'； ②项目名称第三字母 w 小写)

4. ##### 通过命令 amwiki -h 查看帮助或 amwiki -v查看版本，确认 amwiki 安装成功

5. ##### cd 到项目文件夹，创建config.json文件
    - **name**，您的文库名称，设置但为空或不设置将显示默认名
    - **ver**，文本版本号或维护者名号，设置但为空将不显示，注意诺不设置此属性将显示 amWiki 作者
    - **logo**，logo 的 url，设置但为空或不设置将显示默认 logo
    - **colour**，自定义颜色，默认为蓝色
    - **testing**，是否启用接口测试模块，默认值 false  
    - **github-url**，github 项目地址
    - **imports** ，页面嵌入自定义 css、js 文件
    - **page-mounts** ，是否开启页面挂载数据
    - **library-prefix** ，重新定义 library 路径
    - 例如：
    ```javascript
    {
        "name": "洛理指南",
        "ver": "by AjiaErin",
        "colour": "50,205,50",
        "logo": "https://image.gaoajia.com/lit-ajia-ltd/logo.png",
        "testing": false,
        "github-url": "https://github.com/gaoajia/lit-homepage/",
        "imports": 
            [
             "assets/test.css",
             "http://cdn.bootcss.com/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML",
             "assets/test.js"
            ],
        "page-mounts": true,
        "library-prefix": "/admin/dev-wiki"
    }  
    ```
1. ##### 通过命令 amwiki -c 创建新文库

2. ##### 通过命令 amwiki -b 在浏览器中访问刚刚创建的文库
3. ##### 通过命令 amwiki -s 预览开发

## 文库目录结构
项目目录自动生创建的内容如下

    index.html                 // http 访问入口页面
    amWiki/                    // amWiki Web 端程序文件夹
    library/                   // 您的 Markdown 文库目录，所有文件必须使用 .md 格式
       ├ $navigation.md        // amWiki 文库目录导航文件，可自动/手动更新
       ├ 首页.md                // Web 端打开页面时页面页面默认显示的内容
       ├ 001-学习amWiki/        // Markdown 文件夹01
       │   ├ 001-关于amWiki     // 一些 Markdown 文档，支持二级目录
       │   └ 002-...
       ├ 002-文档示范/          // Markdown 文件夹02
       │   ├ 001-通用api        // 一些 Markdown 文档，支持二级目录
       │   └ 002-...
       └ 003-...               // 更多 Markdown 文件夹
    (assetes/)                 // 如果您粘帖截图，图片文件将自动创建在此处


## 关于编辑

1. 新建或更改文件夹和文档名，组织您自己的文档结构 (文档必须使用 .md 扩展名)

2. 编辑 Markdown 文档，制作您自己的文档内容

3. 每个文件夹 id-名称 来命名，每个文件使用 id-名称.md 来命名

4. id 不可删除，删除后将无法正常工作

5. library 文件夹下 home-首页.md 为打开时的默认首页

6. $navigation.md 导航文件描述了整个 library 的结构，此文件一般无需人工维护会自动更新


## 多人维护

可以借助版本管理工具 SVN、Git、Hg，传输协议工具 FTP/SFTP，文件同步工具 Dropbox、百度云等等，实现便捷的多人维护。