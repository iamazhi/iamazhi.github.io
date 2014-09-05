##一、git
###1、分支
   - 查看所有分支（本地+远程分支）
    - git branch -av
   - 新增远程分支
    - git branch branchName
   - 切换分支
    - git checkout branchName
   - 删除远程分支
    - git push origin --delete branchName
   - 执行推送命令，在GitHub远程版本库创建分支gh-pages:
    - git push -u origin gh-pages

##二、GITHUB：
###1、why github:
   - 专一：只用git并且完整支持，单提供替他方式(svn,hg)的访问接口 
   - 在线编辑
   - 社交编程（fork派生&pul request拉拽请求）：从纯技术到社区
   - 非广告收费模式：私有版本库托管、面向企业的版本库托管和项目管理平台、人员招聘等付费服务
   - 细节

###2、主页
   - 个人主页
    - GitHub 为每一个用户分配了一个二级域名user-id.github.io，用户为自己的二级域名创建主页很容易，只要在托管空间下创建一个名为user-id.github.io的版本库，向其master分支提交网站静态页面即可，其中网站首页为index.html。
   - 项目主页
    - 用git symbolic-ref命令将当前工作分支由master切换到一个尚不存在的分支gh-pages。
        > $ git symbolic-ref HEAD refs/heads/gh-pages
    - 删除暂存区文件，即相当于清空暂存区。
        > $ rm .git/index
    - 创建项目首页index.html。
        > $ printf "hello world.\n" > index.html
    - 添加文件index.html到暂存区。
        > $ git add index.html
    - 执行提交。提交完毕分支gh-pages完成创建。
        > $ git commit -m "branch gh-pages init."
    - 执行推送命令，在GitHub远程版本库创建分支gh-pages。
        > $ git push -u origin gh-pages
   - 专有域名 
    - 只要在master分支（用户主页所在版本库）或gh-pages分支（项目版本库）的根目录下检入一个名为CNAME的文件，内容为相应的专有域名。当然还要更改专有域名的域名解析，使得该专有域名的IP地址指向相应的GitHub二级域名的IP地址。

###3、gist
   - 私密gist只是在github中相对安全，但还是会被seo获取。
   - Gist除了被用于粘贴数据（如代码块）并在网页中引用。[gist](https://gist.github.com)
   - Embed:嵌套在网页中
   - 版本库：每一个gist对应一个版本库https://gist.github.com/7003150.git
   - Greasemonkey: 
    - 实现无痕外部js加载
    - 当浏览器安装了 Greasemonkey 或类似插件之后，当访问扩展名为.user.js的URL时，会将该URL指向的JavaScript脚本安装在浏览器中
    - 当访问指定的网址时会自动调用相应的JavaScript脚本，修改相关网页内容或添加特效等等。
