##关于branch

查看分支，*表示当前所在分支

```
git branch
```

创建分支<branchname>

```
git branch <branchname>
```


切换分支至<branchname>

```
git checkout <branchname>
```

创建切换一步到位

```
git checkout -b <branchname>
```

删除分支

```
git branch -d <branchname>
```

当<branchname>分支的代码还未合并到master，上面命令无法删除。这时可以使用强制删除

```
git branch -D <branchname>                                                                                                                            
```