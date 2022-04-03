

#### git 三大区



工作区 ---> git add xxx --> 暂存区 --> git commit -m "提交信息" -->版本区

* 工作区：写代码的文件夹

* 暂存区：暂时保存代码，即将交给 git 进行版本管理

* 版本区：已经被 git 版本控制管理了（空文夹不会被 git 管理）

  

#### git 命令



##### linux 常用命令

* 创建demo文件夹：mkdir demo

* 创建/编辑文件：vi tex.txt 

  进入插入模式：i 
  保存并退出：esc :wq 
  不保存退出：esc :q! 

* 查看当前路径：pwd 
* 列出当前文件夹的所有文件：ls 

* 查看文件：cat test.txt 

* 清屏（CTRL + L）：clear 

  

##### git常用命令

* 配置个人信息
  git config --global user.name "jayce"
  git config --global user.email "1261719702@qq.com"

* 查看配置信息
  git config user.name
  git config user.email

  

* 删除文件夹（删除被git管理的文件）：git rm -r xxx

* 删除文件（删除被git管理的文件）：git rm  xxx.txt

* 初始化 git 仓库：git init 

* 查看文件状态：git status 

* 从工作区提交某个文件到暂存区：git add xxx 

* 从工作区提交全部文件到暂存区：git add *  ，git add .

* 从暂存区提交文件（**全部**）到版本区：git commit -m "提交信息"  

* 对比**暂存区和工作区**的不同：git diff

* 对比**版本区和暂存区**的不同：git diff --cached

* 对比**版本区和工作区**的不同：git diff master

* 查看详细的提交日志（从最新的提交到最旧的提交）：git log

* 查看精简的提交日志：git reflog



###### 版本回退 版本穿梭 版本撤销命令

* 版本回退（回退一次提交）：git reset --hard HEAD^

* 回退到指定版本号的 commit 版本：git reset --hard 版本号

* 用**版本库文件**替换**暂存区**的全部文件：git reset HEAD

* 用**暂存区指定文件**替换**工作区指定文件**（**危险**）：git checkout --x.txt

* 用**版本库文件**替换**工作区和暂存区**的文件（**危险**）：git checkout HEAD x.txt

* 从**暂存区**删除文件：git rm --cached x.txt 

  

###### 分支

* 主分支：master --代码经过开发人员的单元测试以及测试人员的详细测试
* 开发分支：dev --开发人员所有的代码提交到此分支
* 测试分支：test --测试人员用的
* 里程碑分支：tags --记录各个版本的代码

常用命令

* 创建分支 dev （会把当前分支的所有文件复制到 dev 分支）：git checkout -b dev
* 切换到 master 分支：git checkout master
* 查看有多少的分支：git branch
* 合并分支（将 dev 合并到 master，当前分支需为 master）：git merge dev
* 删除 dev 分支（当前分支为 master）：git branch -d dev
* 对比两个分支：git diff master dev
* 对比两个分支有差异的文件列表：git diff master dev --stat
* 对比两个分支指定文件的差异：git diff master dev demo.txt
* 重命名分支：git branch -M main

###### 与 github 交互

* 关联：git remote add origin https://github.com/Jayce-liang/test.git
* 推送：git push -u origin main
* 拉取：
  * git pull origin main
  * git pull
  * git fetch origin main:temp
* 克隆：git clone https://github.com/vuejs/vue.git























