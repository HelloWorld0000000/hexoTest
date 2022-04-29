---
title: Git提交网站到Gitee
categories: Hexo设置
tags: 部署到远程仓库
---

[参考：如何在码云Gitee中部署个人静态网站？git提交网站](https://www.bilibili.com/read/cv6506359)

[参考：git修改相同文件再发送到Gitee仓库](https://www.likecs.com/show-203809491.html)



# 目标/文件

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/1.jpg" alt="1" style="zoom:80%;" /> 

---



# 在码云里面新建一个仓库

### 新建仓库

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/2.jpg" alt="2" style="zoom:80%;" /> 

### 设置仓库信息

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/3.jpg" alt="3" style="zoom:80%;" /> 

### 提示创建仓库完成

**gitee也会给出教程**

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/4.jpg" alt="4" style="zoom:80%;" /> 

---



# 利用Git提交到码云里面仓库里面

### 安装git软件

### 在网站根目录下空白处，右击选择

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/5.jpg" alt="5" style="zoom:80%;" /> 

### 初始化仓库输入一下命令

```
git init
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/6.jpg" alt="6" style="zoom:80%;" /> 

### 把本地文件放入暂存区输入命令 

```
git add .  //注：后面有 点，前后间隔 一个空
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/7.jpg" alt="7" style="zoom:80%;" /> 

### 把暂存区文件放入本地仓库里面

```
git commit -m  '自定义命名'
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/8.jpg" alt="8" style="zoom:80%;" /> 

### 连远程仓库--起别名

```
git remote add 别名 仓库链接  //注：HTTPS链接
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/9.jpg" alt="9" style="zoom:80%;" /> 

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/10.jpg" alt="10" style="zoom:80%;" /> 

**如果失败，提示**：remote origin already exists

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/16.jpg" alt="16" style="zoom:80%;" /> 

**解决办法：**

```
1、先删除远程 Git 仓库
	git remote rm origin
		| 注：如果执行 git remote rm origin 报错的话，我们可以手动修改gitconfig文件的内容
			| vi .git/config
			| 把 [remote “origin”] 那一行删掉就好了。
		
2、重新连接远程仓库
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/15.jpg" alt="15" style="zoom:80%;" /> 

### 把本地仓库推送到码云远程仓库里面

```
git push -u origin 当前分支  
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/11.jpg" alt="11" style="zoom:80%;" /> 

### 重新刷新仓库,会发生变化,已经有网站了

---



# 部署发布静态网站

### **点击仓库上方的 服务**，**选择 Gitee Pages**

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/12.jpg" alt="12" style="zoom:80%;" /> 

### 可以直接点击启动按钮

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/13.jpg" alt="13" style="zoom:80%;" /> 

### 稍等一下,就会出现一个 可访问的域名

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/14.jpg" alt="14" style="zoom:80%;" /> 

---



# 修改相同的文件内容，再次发送到Gitee仓库

#### **【方法一】**

```
注：现在不会有这种问题了，如果之前提交过，现在修改了文件，git会有对应标记，只需要直接
git add . 或者 git add +文件名
git commit -m “注释”
git push origin master
```



#### **【方法二】**

### 新建文件夹

### 初始化一个 git 本地仓库

```
输入： git init
	作用：
		-- 此命令主要是为了初始化一个 git 本地仓库
		-- 此命令运行完之后，会在本地创建一个 .git 的文件夹（隐藏的文件夹）
```

### 删除仓库地址

```
输入： git remote rm origin
	作用：
		-- 删除仓库地址（防止你之前使用到的地址重复）
		--（注：如果你第一次弄可以不打，但是一般打比较保险，发错了仓库会很想哭）
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/17.jpg" alt="17" style="zoom:80%;" /> 

### 连接远程仓库--起别名

```
输入： git remote add 别名 仓库链接  //注：HTTPS链接
	作用：
		-- 将 别名 后面的地址进行替换，替换成你的远程仓库地址
```

### 将远程仓库最新内容拉下来

```
输入： git pull origin master
	作用：
		-- 将远程仓库里不同的东西下载到你的文件夹中，防止文件不同步导致报错
		-- （一般为说明文档和许可证说明）
```

### **查看暂存区的已缓存的文件（git add 进来的文件）**

```
输入： git ls-files 
或输入：git rm --cached +文件名（如git rm --cached a.txt）

	作用：
		-- 输入,之前传输过的,但现在需要修改并重新发送的文件
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/18.jpg" alt="18" style="zoom:80%;" /> 

### **清空当前文件夹的暂存区的【所有】缓存**

```
输入： git rm --cached
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/19.jpg" alt="19" style="zoom:80%;" /> 

### 将已修改好的文件重新添加到暂存区

```
输入： git add 文件名.后缀名
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/20.jpg" alt="20" style="zoom:80%;" /> 

### 把暂存区文件放入本地仓库里面

```
输入： git commit -m  '自定义命名'
```

### 把本地仓库推送到码云远程仓库里面

```
输入：git push origin 当前分支 
```

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/21.jpg" alt="21" style="zoom:80%;" /> 

---



# 解决：GitHub、Gitee上传的 README.md文档的图片显示失败

### 将图片上传到仓库

### 打开图片，复制图片链接：

图1：Gitee

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/22.jpg" alt="22" style="zoom:80%;" />  



图2：GitHub

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/23.jpg" alt="23" style="zoom:80%;" />  



图片上方的链接

![24](Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/24.jpg) 

### 替换 README.md文档内的图片链接

<img src="Git%E6%8F%90%E4%BA%A4%E7%BD%91%E7%AB%99%E5%88%B0Gitee/25.jpg" alt="25" style="zoom:80%;" /> 

