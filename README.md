# 索引
## 命令

> ### [1. clone](#clone)
> ### [2. init](#init)
> ### [3. diff](#diff)
> ### [4. commit](#commit)
> ### [5. status](#status)
> ### [6. log](#log)
> ### [7. branch](#branch)
> ### [8. checkout](#checkout)
> ### [9. merge](#merge)
> ### [10. rebase](#rebase)
> ### [11. remote](#remote)
> ### [12. pull](#pull)
> ### [13. stash](#stash)
> ### [14. fetch](#fetch)
> ### [15. push](#push)
> ### [16. tag](#tag)
> ### [17. gitk](#gitk)
> ### [18. add](#add)
> ### [19. grep](#grep)  
> ### [20. gc](#gc)
> ### [21. gc](#reset)

## 其他
> ### [1. git常用命令(图)](#git常用命令)    
> ### [2. .gitignore文件](#gitignore文件)
> ### [3. .建立空分支](#建立空分支)

# clone
|命令|说明|
|---|---|
|git clone [url]|url 远程地址，克隆一个远程的仓库|
|git clone [url] [dir]|克隆一个远程库到指定的目录中|

# init
|命令|说明|
|---|---|
|git init|初始化一个仓库|
|git init --bare|创建一个裸仓库|

# diff
<table  >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td >git diff</td>
    <td >比较工作目录(working tree)和暂存区域快照(index)之间的差异，即文件的修改和删除，不包含新增的文件</td>
  </tr>
  <tr>
    <td>git diff --cached</td>
    <td>查看暂存区域快照(index)与commit的差别的</td>
  </tr>
  <tr>
    <td>git diff HEAD</td>
    <td>查看工作目录(working tree)和最近一次commit的差别的</td>
  </tr>
  <tr>
    <td style="min-width:300px">git diff [branch_name1]..[branch_name2]</td>
    <td>查看两个分支差异</td>
  </tr>
  <tr>
    <td>git diff [branch_name]</td>
    <td>当前分支工作目录与指定分支的差异</td>
  </tr>
  <tr>
    <td>git diff HEAD -- [path]</td>
    <td>path目录（或文件）与最近一次提交的差异</td>
  </tr>
  <tr>
    <td>git diff --stat</td>
    <td>输出文件更改的行数，不显示具体更改的内容</td>
  </tr>
</table>

# commit
<table  >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td >git commit</td>
    <td >提交索引库（需要输入提交信息）</td>
  </tr>
  <tr>
    <td>git commit -a</td>
    <td>自动把所有内容被修改的文件(不包括新创建的文件)都添加到索引中，并且同时把它们提交</td>
  </tr>
  <tr>
    <td>git commit -m [commit_info]</td>
    <td>简写提交信息，不用每次都进入vi的编辑页面</td>
  </tr>
</table>

# status
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git status</td>
    <td>列出了仓库中修改过的、新创建的、已经暂存但未提交的文件</td>
  </tr>
</table>

# log
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git log</td>
    <td>查看所有提交记录（按q退出）</td>
  </tr>
  <tr>
    <td>git log -p</td>
    <td>显示每次提交的更改（即显示diff）</td>
  </tr>
  <tr>
    <td>git log --stat</td>
    <td>显示在每个提交(commit)中哪些文件被修改了（显示文件增加或删除了多少行）</td>
  </tr>
  <tr>
    <td>git log --graph</td>
    <td>以提交图的形式显示提交记录</td>
  </tr>
  <tr>
    <td>git log --pretty=[pretty_name]</td>
    <td>格式化日志，参数有'medium','full','fuller','email' ,'raw', 'short', 'oneline', 'format'</td>
  </tr>
  <tr>
    <td>git log --reverse</td>
    <td>逆序显示日志</td>
  </tr>  
</table>

# branch
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git branch</td>
    <td>查看所有本地分支，以及当前所处分支</td>
  </tr>
  <tr>
    <td>git branch -a</td>
    <td>查看所有本地分支和远程分支，显示当前所处分支</td>
  </tr>
  <tr>
    <td>git branch [banch_name]</td>
    <td>添加一个新的分支</td>
  </tr>
  <tr>
    <td>git branch [banch_name1] [banch_name2]</td>
    <td>基于 branch_name2 新建一个名为 branch_name1 的分支</td>
  </tr>
  <tr>
    <td>git branch -d [banch_name]</td>
    <td>删除已经合并的分支</td>
  </tr>
  <tr>
    <td>git branch -D [banch_name]</td>
    <td>强制删除一个分支，无论是否合并</td>
  </tr>
  <tr>
    <td>git branch --track [branch_name] origin/[branch_name]</td>
    <td>创建远程分支的追踪分支，简化pull操作，git pull branch_name即可</td>
  </tr>

</table>

# checkout

|命令|说明|
|---|---|
|git checkout [branch_name]|切换到一个已存在的分支|
|git checkout -b [branch_name]|新建一个分支，并进入该分支，-b参数后面可以跟正常的branch操作|
|git checkout [path]|恢复指定的目录或文件到上一次提交的版本|

# merge
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git merge [banch_name]</td>
    <td>将当前分支与指定的分支合并</td>
  </tr>
</table>

# rebase
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git rebase [分支名]</td>
    <td>类似于合并，<a target="_blank" href="http://gitbook.liuhui998.com/4_2.html">详情点这里</a></td>
  </tr>
  <tr>
    <td>git rebase --continue</td>
    <td>rebase有冲突，在解决完冲突后继续执行rebase</td>
  </tr>
</table>

# remote
<table>
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git remote</td>
    <td>显示所有定义的远程库</td>
  </tr>
  <tr>
    <td>git remote add [remote_name] [url]</td>
    <td>新增一个远程库</td>
  </tr>
</table>

# pull
| 命令 | 说明 |
|-----|------|
|git pull|拉取origin地址，并与master合并，origin可以通过 git config --get remote.origin.url 查看|
|git pull [remote_name 或 url] [branch_name] |拉取一个远程仓库，并合并到指定分支中|
|git pull --rebase [remote_name 或 url] [branch_name]|拉取一个远程仓库，并合并（以rebase的形式合并）到指定分支中|
|git pull [remote_name 或 url] [branch_name] --allow-unrelated-histories|当报错：fatal: refusing to merge unrelated histories 时。[具体情况见链接](http://blog.csdn.net/lindexi_gd/article/details/52554159)|


# stash
<table>
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git stash</td>
    <td>将当前工作区存储起来，并且工作区更改为上次提交状态的内容</td>
  </tr>
  <tr>
    <td>git stash apply</td>
    <td>调取上一次的存储</td>
  </tr>
  <tr>
    <td>git stash list</td>
    <td>查看所有的存储列表</td>
  </tr>
  <tr>
    <td>git stash apply stash@{1}</td>
    <td>调取指定的存储，1代表指定存储的编号，编号可以通过git stash list 查看</td>
  </tr>
  <tr>
    <td>git stash clear</td>
    <td>清空存储列表</td>
  </tr>
</table>

# fetch
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git fetch [remote_name]</td>
    <td>拉取一个远程仓库（不合并），可以通过git merge remote_name/master，合并前可以通过git log -p master..remote_name/master 进行差异检查</td>
  </tr>
</table>

# push
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git push [remote_name|url] [本地分支名]:[远程分支名]</td>
    <td>往远程服务器推送更新</td>
  </tr>
  <tr>
    <td>git push [remote_name|url] [本地分支名]</td>
    <td>省略远程分支名，默认与本地同名的分支合并，不存在则新建远程分支名</td>
  </tr>
</table>

# tag
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git tag</td>
    <td>列出所有标签</td>
  </tr>
  <tr>
    <td>git tag -l [search_str]</td>
    <td>搜索指定的标签，search_str可以使用通配符，例如：git tag -l 'v1.4.2. >'</td>
  </tr>
  <tr>
    <td>git tag [tag_name] [commit_sha]</td>
    <td>给某一次提交打标签</td>
  </tr>
</table>

# gitk
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>gitk</td>
    <td>图形化界面</td>
  </tr>
</table>

# add
<table >
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td >git add [path1] [path2]</td>
    <td > path表示指定的文件名或目录，如果path是目录则添加该目录下的所有文件更改(包含修改，删除，新增)</td>
  </tr>
  <tr>
    <td>git add --all, git add -A, git add .</td>
    <td> 提交所有更改（包含修改，删除，新增）</td>
  </tr>
  <tr>
    <td>git add -u, git add --update </td>
    <td>提交已存在于索引库中的文件，即文件的删除和修改，不提交当前新增的文件。</td>
  </tr>
  <tr>
    <td>git add --ignore-removal .</td>
    <td>提交文件修改和新增，忽略删除文件</td>
  </tr>
  <tr>
    <td>git add -i</td>
    <td>开启一个界面，可以选择一些add相关的操作</td>
  </tr>
</table>

![](http://upload-images.jianshu.io/upload_images/4110638-973ddf93cb25c0cc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# reset
| 命令 | 说明 |
|-----|------|
|git reset --hard HEAD|将工作目录恢复到上一次提交的状态（不恢复当前新建的文件，即未加入索引库的文件）|

# revert
| 命令 | 说明 |
|-----|------|
|git revert HEAD|撤销上一次的提交|
|git revert HEAD^|撤销上上次的提交|
|git revert HEAD~1|~号加数字n，表示撤销前n次提交|

# grep
<table>
  <tr><th>命令</th><th>说明</th></tr>
  <tr>
    <td>git grep [str]</td>
    <td>搜索指定的文件内容</td>
  </tr>
  <tr>
    <td>git grep [str] [path|SHA|tag]</td>
    <td>在指定的路径（或者文件名），提交的SHA，标签名，中搜索指定的文件内容</td>
  </tr>
  <tr>
    <td>git grep -n [str]</td>
    <td>搜索指定的文件内容，并且显示对应的行号</td>
  </tr>
  <tr>
    <td>git grep --name-only [str]</td>
    <td>搜索指定的文件内容，只显示包含该内容的文件名</td>
  </tr>
  <tr>
    <td>git grep -a [str]</td>
    <td>搜索指定的文件内容，显示 文件:匹配行数 ，例如 test.txt:2</td>
  </tr>
  <tr>
    <td>git grep -e [条件1] --and -e [条件2]</td>
    <td>且操作，搜索同时出现 条件1 和 条件2 的行</td>
  </tr>   
    <tr>
    <td>git grep --all-match -e [条件1] -e [条件2]</td>
    <td>或操作，搜索出现 条件1 或者出现 条件2 的行</td>
  </tr>
  </tr>   
    <tr>
    <td>git grep -e [条件1] --and \( -e [条件2] -e [条件3] \) </td>
    <td>且与或混用操作，搜索出现 条件1 并且出现 条件2 或 条件3 的行，注意这里的<b> \( 之后 </b>和<b> \) 之前 </b>都必须加空格</td>
  </tr> 
</table>

# gc
| 命令 | 说明 |
|-----|------|
|git gc|压缩git日志|

---

# 其他

### git常用命令

![git常用命令](http://upload-images.jianshu.io/upload_images/4110638-b260420de12c53ab.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### .gitignore文件
```
# 忽略掉所有文件名是 foo.txt 的文件.
foo.txt

# 忽略所有生成的 html 文件,
.html

# foo.html是手工维护的，所以例外.
!foo.html

#  忽略所有.o 和 .a文件.
.[oa]

# 忽略所有目录下的.vscode文件
**/.vscode
```

### 建立空分支
```
$git symbolic-ref HEAD refs/heads/[name]

$rm .git/index

$git clean -fdx 
```
