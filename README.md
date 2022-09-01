# git 学习
[progit](https://git-scm.com/book/en/v2)

[progit-cn](https://www.progit.cn/)

查看当前仓库状态
```sh
git status

# 省略版
git status -s
# 或
git status --short
# ?? --> 未添加到仓库的文件
# M  --> 修改的文件
# A  --> 新加入的文件
```

不追踪的文件 -- `.gitignore`

![image](https://user-images.githubusercontent.com/35592711/187822573-33604a57-d0b2-4235-b59a-20cb391b56fd.png)

有时候不起作用原因：新建的文件在git中会有缓存，如果某些文件已经被纳入了版本管理中，就算是在.gitignore中已经声明了忽略路径也是不起作用的，这时候我们就应该先把本地缓存删除，然后再进行git的push，这样就不会出现忽略的文件了。git清除本地缓存命令如下：
```sh
git rm -r --cached .
git add .
git commit -m 'update .gitignore'
```

查看已经提交的文件内容
```sh
# 如果已经提交(commit) git diff 无输出

# 最近的提交内容，两条语句一样
git diff --staged 
git diff --cached 
```

