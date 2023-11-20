```

git -v
git config --global user.name "TianPeng Hu" //配置用户名
git config --global user.email 2928121096@qq.com //配置邮箱
git config --global credntial.helper store //保存密码
git config --global --list //查看配置

git init 仓库初始化
git clone 克隆一个已经存在的仓库

git本地管理分为三个部分，工作区.gti所在的目录，暂存区.git/index，本地仓库.git/objects
文件状态：
未跟踪Untrack
未修改Unmodified
已修改Modified
已暂存Staded

git status 查看当前仓库状态

git add 提交文件到暂存区
git add . 所有文件
git add *.txt 所有的txt文件
git ls-files 查看版本区的文件

git commit 只会把暂存区的文件提交到本地仓库
git commit -m //

git log 查看提交记录
git log --oneline更简洁的信息
git reflog 查看所有操作记录

git reset: 回退到某一个版本 
git reset --soft 工作区和暂存区都保留 后面加版本号或者Head^ Head^^上一次和上上次
git reset --hard 工作区和暂存区都清空
git reset --mixed 默认，工作区保留，暂存区清空

git diff 比较文件差异内容，不加参数默认工作区和暂存区
git diff HEAD 工作区与版本区
git diff --cached 暂存区与版本区
还可以比较两个版本的差异，只需在后面加上版本号
git diff f239bc3 d4091c7
HEAD指向分支的最新提交节点
git diff fe7dbd7 HEAD
HEAD~n 指向HEAD版本之前的n个版本

版本库中删除文件
1. 现在工作区删除文件，然后更新到暂存区，最后提交
2.
git rm 文件名 把文件从工作区和暂存区同时删除
git rm --cached 文件名 从暂存区中删除文件，但保留在当前工作区
删除后不要忘记提交

.gitignore文件 ignore忽略
如
文件夹/
README.MD
*.TXT
.gitignore文件生效有一个前提，就是不能是已经提交到版本库中的文件


github ssh配置
进入根目录 cd
输入 ssh-keygen -t rsa -b 4096 回车
然后命名。会生成两个文件。一个是命名的无后缀(私钥)，一个是命名的.hub文件(公钥)，打开公钥复制里面的内容，然后回到GitHub进行配置。

同步本地仓库和远程仓库
git pull 远程=》本地
git push 本地=》远程

git remote add origin关联本地与远程
git remote -v查看当前仓库对应远程仓库的别名和地址

git push -u origin main:main 将本地仓库与远程仓库的main分支相关联


git branch 分支名 创建新的分支（但并没有切换）
git checkout 分支名 切换分支

git checkout不仅可以切换分支，还可以恢复文件。所以如果分支名与文件名相同，会默认切换分支。为了避免歧义还可以用git switch切换分支

git merge 分支名可以将分支合并到当前分支中,合并后分支不会消失。不使用了可以git branch -d 分支名
删除，如果没有合并的话需要git branch -D 分支名才能强制删除

git rebase main 将当前分支dev变基到main分支，顺序在main分支之后。因为rebase会找到
两个分支的共同祖先，然后将dev分支嫁接到main分支后

```
merage:bao
分支冲突：
```


```
