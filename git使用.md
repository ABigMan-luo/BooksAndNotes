git的简单配置：

	git config --global user.name "ABigMan-luo"
	git config --global user.email "1093776961@qq.com"
	git config --global --list

git建立仓库：

	已有文件夹，进入该文件夹，执行
	git init
	
	还没有创建文件夹：
	git init filename

git本地仓库用户信息的配置

	git config --local 只对当前仓库生效
	git config --global 对电脑当前登陆用户所有仓库有效
	git config --system 对电脑所有用户的所有仓库有效
	优先级依次递减

git提交版本

	在仓库中：
	git add filename  将文件放入缓存区
	git add .  将所有的文件放入缓存区
	git commit -m "备足版本的信息”  提交到远程仓库
	git log 查看版本信息

git版本状态查看

	git status 查看当前本地状态
	git status -s 简短方式显示状态，红色代表没有提交，M表示修改，??表示新的文件

git查看历史版本

	git log 显示所有历史信息
	git log --pretty=oneline 只显示一行
	git log -p 显示版本之间的差别
	git log -5 显示最近的5个版本
	git log -5 -p
	git log stat 显示一些统计信息

git 使用 .gitignore 文件忽略提交的文件

	#  表示注释
	使用glob表达式：
		* 匹配任意数量的字符
		[abc] 匹配其中的一个字符
		? 匹配一个任意字符
		/  以/结尾 表示一个文件夹
		!  取反

git 内容对比

	git diff 显示在没有提交到缓存区的时候，显示修改的内容

git 省略add步骤，直接添加到远程仓库

	git commit -a -m "版本信息"

git 版本之间的对比

	git diff 老版本哈希值  新版本哈希值   显示了新版本的变化
	git diff --staged 显示提交到缓存区的版本的变化

git 的撤销与删除

	git restore filename  撤销本地的文件内容修改
	git restore --staged filename 撤销缓存区增加的文件
	git rm filename 从版本控制中删除文件
	git rm --cached file 删除文件，保留本地文件

git 所有操作都需要提交  git commit -m ""

git 移动文件

	git mv oldfilename newfilename

git 版本补录

	git commit amend -a 将修改提交到最近修改的版本，不产生新的版本

git 的标签

	git tag -a tagname -m "提交信息" 
	git tag tagname  都是给当前版本添加标签
	git tag 显示所有标签
	git tag -l 正则表达式  显示符合条件的标签
	git tag -a tagname version -m "信息"  版本补录
	git tag -d tagname 删除标签

git 检出

	git checkout versionId/tagname 将当前的头节点返回到指定的版本
	git reflog 显示所有的版本，包括当前头版本以后的版本

git 别名

	git config --global alias.ol 'log --pretty=oneline' 将log --pretty=oneline  的别名为log

git 的远程地址

	git remote add urlName url  添加远程仓库地址
	
git 远程仓库
	git remote show urlName  查看远程仓库的信息
	git push study master 将本地仓库推到远程仓库，study 是仓库地址名字，master是分支的名字
	git fetch study  拉取远程仓库到本地
	git pull study 拉取远程仓库
	
git 远程仓库名称
	git remote remane oldname newname  修改远程仓库名称
	git remote rm urlName 删除远程地址
	
git 克隆

	git clone url 将别人的项目下载到本地