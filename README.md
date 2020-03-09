# git_test
测试git及GitHub的基本功能

一.git环境配置好之后，直接使用“git clone 仓库地址”即可将远程仓库克隆到本地。
  需要注意的是，如果本地存在两个git账户，则需要取消全局的用户名等设置，且在 .git/config文件中配置对应的账户信息（用户名、邮箱）。
  克隆之后进入本地仓库，使用“git config user.name”和“git config user.email”配置本仓库的账户信息。
  
二.当远程仓库存在多个分支时，需要将A分支的change合并到B分支，有如下办法：
  1.在远程仓库中使用“pull request”，将A指令中的change合并到B，但是会自动生成merge的change。
  2.在本地直接使用rebase A，这样会导致A覆盖B，push时会报错，按照提示pull B会自动合并，也会生成merge的change。
  3.在本地使用cherry-pick [A change]，如果存在冲突则需要手动修改，不会生成自动merge的change，推荐该办法。

三.push的用法如下：
  git push <远程主机名> <本地分支名>:<远程分支名>