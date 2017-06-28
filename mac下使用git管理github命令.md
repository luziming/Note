## mac下使用git管理github命令


#### git --version 查看git版本,检查是否安装
#### 通过git上传代码

1. 首先在github新建仓库,在GitHub上的这个仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。
2. 我在本地地搭建一个名称相同的项目，现在想把这个项目通过git上传到github上。首先跳转到项目目录，然后执行 `git init` ，瞬间Git就把仓库建好了，而且告诉你是一个空的仓库（empty Git repository），可以发现当前目录下多了一个.git的目录，这个目录是Git来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。如果你没有看到.git目录，那是因为这个目录默认是隐藏的，用ls -ah命令就可以看见。
3. 用命令 `git add` 告诉Git（可以使用  `git add file git add <foler>/* 或者 git  add *` ），把文件添加到仓库,使用命令git add <file>，注意，可反复多次使用，添加多个文件，执行git add *，没有任何提示，如下图所示，执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。
4. 用命令git commit告诉Git，把文件提交到仓库 

 	`git commit -m "这里添加,提交内容注释"`

5. 添加远程库，目前，在GitHub上的这个仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

	现在，我们根据GitHub的提示，在本地的仓库下运行命令：
	
	`git remote add orgin SSH Key`

	远程库的名字就是origin，这是Git默认的叫法，也可以改成别的，但是origin这个名字一看就知道是远程库。而SSH Key可以直接去github shortrent repository 页面点击【Clone or download】去复制SSH Key
	
	`例如我自己的: git remote add origin git@github.com:luziming/Note.git `

6. 把本地库的所有内容推送到远程库上，执行

	`git push -u origin master`


	由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。

7. 更新仓库
	
	`git pull origin master`


### 这是新建项目并提交代码的全部步骤,后来秩序执行3,4,5,6即可

#### [如果是第一次使用,需要创建SSH关联github,看这里即可](http://blog.csdn.net/believejava/article/details/51523345)