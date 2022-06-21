# 任さんはすごいですね。

[**官方文档**](https://docs.github.com/)

[**markdown语法**](https://www.markdownguide.org/cheat-sheet/)

[**git使用方法（远程关联仓库）**](https://blog.csdn.net/qq_45893260/article/details/118874601)

[**git 获取token的办法/有啥不会官方文档**](https://docs.github.com/cn/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

[**git查看/删除远程仓库**](https://www.csdn.net/tags/MtTaQgwsNzMyODgtYmxvZwO0O0OO0O0O.html)

- [X] **github创建分支与请求合并p**
> 可以在仓库某个版本的基础上，进行修改。每个文件修改后进行一次提交。最后通过pullrequest进行提交，管>理者审核并合并分支。
> 注意两点:
>
> 1. 在哪个分支下创建新的分支，就是以那个分支为基础
> 2. 进行合并分支请求的时候，可以选择比较的对象，比较的对象就会是你请求合并的分支。管理员同意后，请求的分支会变成你修改后的样子。

- [X] **git克隆云端仓库到本地**
> git clone ____对应分支下点击右上角绿色的CODE获得的地址____;
> 关于账号密码：本地的那一套账号密码只是用于一种标识的作用，和github的账号密码没有什么关系。

- [X] **git本地与云端仓库关联**
> 简单的说，通过云端仓库的网址可以本地关联那个仓库。然后比较重要的事情是，如果在云端加了文件，本地是没有办法push上去的，因为本地的git记录里没有那个文件，两边不一致。
> ```
> error: failed to push some refs to 你的仓库网址
> ```
> 另一间比较重要的事情是，本地保存到云端，本质是远程和本地有两个完全一样的分支，包括名字（当然这是在修改前），然后本地经过一系列的修改，再上传到云端。
>
> 通过以下方法解决仓库管理文件和本地不一致的情况
> ```
> $ git pull --rebase origin master
> ```
> 可以把远程最近的更改拉取到本地。之后就可以成功。（多人协作开发过程中经常可能发生这种远端仓库在我还没有提交的时候就被改了的情况）
>
> 具体作用就是复制仓库，然后应用你的提交，将仓库进行修改。
>
> 总结：pull等于远程拉到本地，push等于本地传到远程。

- [X] **git如何以本地已有的项目为基础，创建一个新的远程仓库**

> 首先本地创建项目，初始化之后需要提交一次（不然就是空文件夹），**<font color =red>远程和本地的比较比的都是提交之后的东西。</font>**
>
> 然后看图即可
>
> ![](./img/20220621_%E6%9C%AC%E5%9C%B0%E6%96%87%E4%BB%B6%E5%A4%B9%E5%88%9B%E5%BB%BA%E8%BF%9C%E7%A8%8B%E4%BB%93%E5%BA%93.PNG)
>
> git branch -M 因该是更改分支名的意思。
>
> 然后关联远程仓库。（所有远程相关指令可以用git remote -h查看）
>
> git remote remove origin可以删除已有的远程关联，如果你写错了的话（git remote -v可以查看当前的关联网址）
>
> git push的过程就是将本地提交结果拷贝到远程相同分支的过程。

- [X] **git如何克隆远程仓库并修改对应分支**

> 首先本地clone
> 网址由github完整网址/用户名/仓库名.git组成
>
> ```git clone https://github.com/outputlimitexceed/git-learning.git```
>
> 然后本地切换分支
>
> ```git checkout 分支名```
>
> 进行修改并提交，不commit就没有区别
>
> 最后需要push上去
>
> ```git push origin 分支名```
