1. git clone + [仓库地址] 
2. git clone -o [修改远程主机名] [仓库地址]
3. git remote -v  查看本地仓库所关联的远程仓库信息
4. git status 查看整个仓库的状态

5. git add [修改] 将修改添加至暂存区
6. git add . 命令全部添加至暂存区

7. git reset -- [文件名] 或 git rm --cached [文件名]  撤销暂存区修改
8. git reset -- 将暂存区的全部修改撤销

9. git diff --cached 查看暂存区的全部修改
10.git log [分支名] 查看某分支的提交历史，不写分支名查看当前所在分支
11.git log --oneline 一行显示提交历史
12.git log --reverse 正序查看信息
13.git log -n 其中 n 是数字，查看最近 n 个提交
14.git log --author [贡献者名字] 查看指定贡献者的提交记录
15.git log --graph 图示法显示提交历史
16.cat -n ~/.gitconfig 查看配置信息

17.git commit -m '备注' 提交至版本区
18.git push 提交至远程仓库
19.git push -f 强制i提交至远程仓库

20.git branch -avv 查看分支信息

21.git reset --soft HEAD^   撤销一次提交
22.git reset --soft HEAD^^  撤销两次提交
23.git reset --soft HEAD~n  撤销n次提交

24.git reflog 查看记录在本地n仓库所有分支的每一次版本变化
25.git reset --hard [版本号] 回退到...

26.1末尾加n任意字段作为本地仓库的主目录名
