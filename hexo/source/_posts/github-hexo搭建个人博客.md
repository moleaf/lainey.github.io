---
title: github+hexo搭建个人博客
date: 2016-11-23 15:13:57
categories: hexo
tags: 
- hexo
---
非安利贴，纯技术干货，按步骤做实测有效~

## **github**

### **git安装**
1.[git下载](https://git-scm.com/download/win)  自行安装  
2.打开git  输入命令  ssh-keygen -t rsa -C "youremailaddress" youremailaddress替换成自己的邮箱地址，它会要你输入密码，直接回车不设密码即可
### *github配置*  
1.首先上[github官网](https://github.com/)上创建属于自己的个人账户，账户名记为*username*
2.然后新建一个repository, 名字取为 username.github.io  （username替换成自己的用户名）其他默认就行
3.如果是第一次使用还需要再本机上生成秘钥并添加到自己的github账户上
    在github上点击自己的账户，找到Settings ->  SSH and GPG keys -> New SSH key title随便写，然后在电脑里找 C:\Users\username\.ssh   username是你的电脑账户名，在该文件夹下有id_rsa.pub文件，用记事本打开，全选复制到key框中 -> Add SSH key 
## **hexo**
### **安装**
1.安装nodejs      [下载地址](https://nodejs.org/zh-cn/)  自行安装
2.安装hexo          cmd下输入  npm install -g hexo-cli
### **配置**
```
$ hexo init <folder>         <folder>名字自取，设置为自己的工作目录，可以取hexo
$ cd <folder>
$ npm install
$ npm install hexo-deployer-git --save
```
### **进行本地预览**
```
$ hexo g
$ hexo s          可以在浏览器网址处输入localhost:4000查看效果
```
### **部署到自己的github**
在 folder 下找到 _config.yml文件，修改最后面的deploy项保存
```
deploy:
  type: git
  repo: git@github.com:username/username.github.io.git    username为你的github账户名
  branch: master
```
```
$ hexo d
```
部署完成，在浏览器上输入 username.github.io查看自己的个人博客了


## **个性化主题定制**
若觉得默认的页面好看可以直接用默认的，不必做这一步
在[主题列表](https://hexo.io/themes/) 中找到自己喜欢的主题，然后进相应网站找到about页面，有主题作者的github，跟着作者的readme做就行啦！！！ 
大致步骤(以aloha为例)
```
$ cd folder      folder为自己的hexo工作目录
$ git clone https://github.com/henryhuang/hexo-theme-aloha.git  themes/aloha   

```
修改配置文件 folder/_config.yml 保存
```
title:  Jack's blog       标题自己起
language: zh-CN           en是英语   zh-CN中文    
theme: aloha
```
查看效果
```
$ cd folder
$ hexo g
$ hexo s     去localhost:4000预览
$ hexo d     部署到github 到username.github.io查看效果
```


## **开始写作**
1.要新建一篇文章
```
$ hexo new title        title是自己起的文章标题
```
2.然后就到 folder/source/_posts   找到文章进行编辑保存，注意文章自带的头文件不可以删除
文章编辑完成后进行hexo三部曲就ok啦~
```
$hexo g
$hexo s
$hexo d                  hexo d -g  生成加部署   hexo s -g 生成加预览     
```


## **参考**
1.[hexo官网](https://hexo.io/zh-cn/docs/index.html)
2.[手把手教你使用Hexo + Github Pages搭建个人独立博客](http://jiji262.github.io/2016/04/15/2016-04-15-hexo-github-pages-blog/)



## **推荐**
默认是使用markdown语法哟，本地建议使用马克飞象编辑markdown，还可以同步到印象笔记~
