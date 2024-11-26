# Basic commands

`$ git init`
> 建立新的本地端 Repository

`$ git clone [Repository URL]`
> 複製遠端的 Repository 檔案到本地端

`$ git status`
> 檢查本地端檔案異動狀態

`$ git add [File or Dir]`
> 將指定的檔案（或資料夾）加入版本控制。用 git add . 可加入全部

`$ git commit`
> 提交（commit）目前的異動

`$ git commit -m "Content"`
> 提交（commit）目前的異動並透過 -m 參數設定摘要說明文字

`$ git stash`
> 獲取目前工作目錄的 dirty state，並保存到一個未完成變更的 stack，以方便隨時回復至當初的 state

`$ git log`
> 查看先前的 commit 記錄

`$ git pull`
> 將遠端的 commit 拉回本地端 Repository
> fetch下來直接merge

`$ git pull --rebase`
> Ex.
> 假設merge前是這樣：
>       D---E master
>      /
> A---B---C---F origin/master
>
> 使用merge後：
>       D--------E
>      /          \
> A---B---C---F----G   master, origin/master
>
> 用rebase：
> A---B---C---F---D'---E'   master, origin/master

`$ git fetch`
> 遠端的數據庫有了新的 Commit 版本，需要將這些更新取回本地端
> 所有有更新的brach都取回
> 下載同步所需的資料，但不會更新任何的檔案
> 先下載下來，沒有merge

`$ git merge origin/master`
> merge code

`$ git push`
> 由 git fetch 將檔案從遠端抓取下來，並使用 git fetch 指令將最新進度加到當前的分支

`$ git push origin [BRANCH_NAME]`
> 發佈至遠端指定的分支（Branch）

**Branch
`$ git branch`
> 查看分支

`$ git branch [BRANCH_NAME]`
> 建立分支

`$ git branch -a`
> 查看所有branch

`$ git branch -D [BRANCH_NAME]`
> 強制刪除指定分支（須先切換至其他分支再做刪除）
> -D -> 強制刪除

`$ git branch -m <OLD_BRANCH_NAME> <NEW_BRANCH_NAME>`
> 修改分支名稱

**Checkout
`$ git checkout [BRANCH_NAME]`
> 取出指定的分支

`$ git checkout -b [BRANCH_NAME]`
> 建立並跳到該分支

`$ git checkout [HASH]`
> 切換到指定的 commit（與 git checkout [BRANCH_NAME] 相同)

**Reset
`$ git reset --hard [HASH]`
> 強制恢復到指定的 commit（透過 Hash 值）

`$ git reset --soft HEAD^`
> 發送 Pull Request 後，又需要修改目前 Branch 程式
> HEAD^ 代表回到上一個 commit，如果要回到多個 commit 請用 HEAD~4，其中 4 請換成您要的數字

**Rebase
`$ git rebase -i commit_id`
> 合併多個commit

`$ git rebase --continue`
> 如果遇到衝突
> git add XXX
> git rebase --continue

`$ git rebase --abort`
> 跳出rebase

**Config
`$ git config --list`
> 查看設定
> = git config -l

`$ git config --local user.name "(userName)"`
> 設定帳號(針對某個設定庫)

`$ git config --local user.email "(e-mail)"`
> 設定e-mail(針對某個設定庫)

`$ git config --global user.name "(userName)"`
> 設定帳號(全域)

`git config --global user.email "(e-mail)"`
> 設定e-mail(全域)

`$ git help`
> 查詢Git指令

**Tool
`$ tig`
> 很直觀看目前branch所有commit log的小工具
