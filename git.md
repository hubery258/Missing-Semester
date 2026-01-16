# GIT brief introduction from cs50
[course link](https://www.youtube.com/watch?v=MJUJ4wbFm_A&t=26s)

## ❓what is git and what can it do for me?
- 代码/文件管理工具
- Keeps track of changes to code
- Test changes to code without losing the original
- Revert back to old versions of code.

## git 指令
- `git clone <url>`，从远程仓库(*repositories*)中copy一份，存在自己的电脑里
- `git add <filename>` 提交一个文件到缓冲区:
    - `git add .` 全部提交
- `git diff`显示所有未add的修改
- `git commit -m "message" ` 把缓冲区的内容提交到分支：
    - `git commit -am "message" `可实现add和commit两步合并
    - `-am` 会把已被 Git 跟踪（tracked）的已改文件自动暂存并提交，但不会包括未被跟踪（untracked/new）文件。要提交新文件仍需先 `git add`。
- `git push`提交到远程仓库（没有访问权的话必须要先pull request）
- `git status` 仓库状态，你现在在哪个branch，文件情况
- `git pull`把线上仓库更改下载到本地仓库，可能出现**merge conflict**
    - merge conflict example:
    ```
    <<<<<<<<<<HEAD
    int b = 2;  （你的修改）
    ============
    int b = 0;  (别人的修改)
    >>>>>>>>>> 哈希值，标识提交
    ```
    只需要删去一条，比如只保留`int b = 2;`或者把两条按自己的方式合并一下。
- `git log`查看提交等等日志
- `git reset`回滚：
    - `git reset --hard <commit>` 输入需要的提交hash值，可在log里查到
    - `git reset --hard origin/master` 回滚到remote branch
- `git branch` 显示所有branch
    - `git branch <name>` 创建新的branch
    - `git checkout <name>` 跳转到对应branch
    - `git checkout -b <name>`同时完成上面两个操作
- `git merge <name>`把某一分支与当前所在分支merge，merge到当前这个分支
- `git branch -D <name>`删除分支
- `pull request`对他人的库修改后提交的request，希望能merge，见github。 