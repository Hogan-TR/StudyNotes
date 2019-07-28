1. **基础操作**
    ```shell
    git clone [仓库地址]
    git clone -o [修改远程主机名] [仓库地址]
    git clone [仓库地址] 		     # 末尾加任意字段作为本地仓库的主目录名
    ```

    ```bash
    git add [修改]                  # 将修改添加至暂存区
    git add .                      # 命令全部添加至暂存区
    ```

    ```shell
    git status                     # 查看整个仓库的状态
    ```
    ```shell
    git branch -avv                # 查看分支信息
    ```
    ```shell
    git remote -v                  # 查看本地仓库所关联的远程仓库信息
    ```

    ```shell
    git diff --cached              # 查看暂存区的全部修改
    ```

    ```shell
    git log [分支名]                # 查看某分支的提交历史，不写分支名查看当前所在分支
    git log --oneline              # 一行显示提交历史
    git log --reverse              # 正序查看信息
    git log -n                     # 其中n为数字，查看最近n个提交
    git log --author [贡献者名字]    # 查看指定贡献者的提交记录
    git log --graph                # 图示法显示提交历史
    git reflog                     # 查看记录在本地n仓库所有分支的每一次版本变化
    ```

    ```shell
    cat -n ~/.gitconfig            # 查看配置信息
    ```

    ```shell
    git commit -m '备注'            # 提交至版本区
    ```

    ```shell
    git push                       # 提交至远程仓库
    git push -f                    # 强制i提交至远程仓库，一般回退后push
    ```

    ```shell
    git reset --                   # 将暂存区的全部修改撤销
    git reset -- [文件名]/git rm --cached [文件名]     # 撤销暂存区修改
    git reset --soft HEAD^         # 撤销一次提交
    git reset --soft HEAD^^        # 撤销两次提交
    git reset --soft HEAD~n        # 撤销n次提交
    git reset --hard [版本号]       # 回退到...
    ```

2. **分支的新建与合并**
```
新建一个分支同时切换到那个分支上
git checkout -b [分支名]
等同于
git branch [分支名]
git checkout [分支名]
```

```
合并分支
git merge [分支名]
```

```
删除分支
git branch -d [分支名]
```

