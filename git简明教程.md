##Git简明教程
<br/><br/>

首先搞清楚 工作区->暂存区->版本库 概念

**配置身份**

```
git config --global user.name "Tony"
git config --global user.email "tony@gmail.com"
```

查询身份	
	
```
git config --global user.name 
git config --global user.email 
```

###命令行进入到项目的根目录下

<br />

**创建代码仓库**	

```
git init 
```

根目录下的`.gitignore`（如果存在）会把每一行指定的文件或目录排除在版本控制之外。

<br />
<br />

**添加要提交的内容**

```
git add <参数>

<参数>：
.    		表示添加所有文件
<目录名> 	添加目录下所有文件
<文件完整名>	添加文件
```




add只是添加，而commit才是提交


**提交**

```
git commit -m "First commit"
```
commit 命令的后面我们一定要通过-m参数来加上提交的描述信息,没有描述信息的提交被认为是不合法的！





**查看文件修改情况**			

```
git status  	
```


**查看到所有文件的更改内容。减号代表删除的部分,加号代表添加的部分**

```
git diff 		
```
**查看特定文件更改内容**			

```
git diff src/com/example/providertest/MainActivity.java 
```

####撤销修改

1. 修改后，文件没有放入暂存区（即文件一直在工作区）：用`git checkout -- 文件名` 撤销工作区的改动（回到跟版本库一样的状态，即回到最近一次 `git commit`时的状态，所有改动全部清除）

2. 修改后，文件放入暂存区，且文件没有再次修改（即文件已经进入暂存区）：分两步：先用 `git reset <文件名>` 撤销 `git add` 操作（此时更改仍留在工作区），再执行 `git checkout -- 文件名` 清除工作区的改动

3. 修改后，文件放入暂存区，且文件再次修改：分三步：先用 `git checkout -- 文件名` 撤销工作区的改动，再用 `git reset <文件名>` 撤销 `git add` 操作（此时更改仍留在工作区），最后执行 `git checkout -- 文件名` 清除工作区的改动

通过 `git checkout -- 文件名` 命令可以撤销文件在工作区的修改。  
通过 `git reset 文件名` 命令可以撤销指定文件的 `git add` 操作，即这个文件在暂存区的修改。  
通过 `git reset` 命令可以撤销之前的所有 `git add` 操作，即在暂存区的修改。


**`git checkout -- 文件名` 命令中的 `--` 表示命令行在 `--` 之后没有更多的选项。这样的好处是，如果碰巧有一个分支与文件名重名，仍然可以恢复该文件，而不是切换到同名的分支。**


**撤销未commit的修改**		


**查看提交记录** 			

```
git log
```
**查看特定提交记录**
			
```	
git log 2e7c0547af28cc1e9f303a4a1126fddbb704281b -1      //注意这里是1
```


**查看特定提交记录中修改的内容** 
	
```
git log 2e7c0547af28cc1e9f303a4a1126fddbb704281b -1 –p
```
