# git
## git 的分支指令<br>
  总所周知，在日常开发中，我们需要把测试服务器和正式服务器分开。相应的，为了保持正式版本能正常运行，我们需要新建一个git分支用来专门的存放正式版APP的源码。<br>
这样，每当我们生成一个版本的时候，我们都可以把稳定版本的源码放到online这个分支上。然后在master分支上继续开发新功能。当需要升级版本的时候，我们只需要把master分支上成熟的代码推送到online分支即可。<br>
### 1、创建新分支

    //新建online分支<br>
    git checkout -b online<br>
### 2、查看当前所有分支

    //查看当前所有的分支<br>
    git branch -a<br>
    //结果显示带*号的，而且颜色是绿色的即为我们当前所在的分支<br>
    *master<br>
    online<br>
### 3、切换分支

    //从当前的master分支切换到online分支上面<br>
    git checkout online<br>
    //此时可以查看分支,使用git branch即可看到master和online分支<br>
    git branch<br>
### 4、删除分支

    //删除online分支<br>
    git branch -d online<br>
### 5、本地合并新分支代码

    //origin是本地默认的一个名称，自己在新建本地仓库的时候是可以改名的<br>
    //平常使用的git pull都是默认从master分支上拉去代码。这里是从online分支上拉取代码<br>
    git pull origin online<br>
### 6、本地提交代码到新的分支

    //这里和上面的git pull差不多。是提交本地代码到online分支<br>
    git push origin online<br>
### ！注意
  1、远程新建分支之后，本地如果立刻使用 git branch -a 查看分支的话，会看不到新建的分支。需要现在本地git pull一下。<br>

   2、如果我们已经通过git checkout master，切换到了master分支。那么我们在本地通过git pull和git push 都可以直接拉去或提交代码到master分支。git会默认使用你当前所在的分支<br>

