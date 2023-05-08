> 本文档更新一下多人协作开发的fork操作需要注意的问题



> 根据之前的文档步骤：创建了一个fork仓库后，你会在你本地目录中修改更新，然后将更新push到自己的fork仓库中，最后再
>
> 在fork仓库中创建pull request!
>
> > ***那么现在产生了一个问题***，你push操作的对象是你fork后的仓库, 这时在本地目录中建立的remote是fork仓库的地址，当你需要再次更改，并且别人已经在原始的仓库中做出了修改，你需要先使用git pull命令将本地的fork仓库更新，但此时remote连接不是原始仓库，你需要在本地fork目录的git bash中先修改remote连接，再拉取更新：
>
> > 具体的命令：
> >
> > git remote set-url origin 原始仓库的url
> >
> > ***注释：上一句将fork仓库连接到原始仓库，这时请使用  git pull 命令更新仓库***
> >
> > ***更新完后，你在自己的fork仓库的本地目录中作出修改，现在需要将更新提交到fork仓库后再做出pull requet，但是现在的remote连接着原始仓库***
> >
> > 现在使用：
> >
> > git remote set-url origin 你fork仓库的url
> >
> > ***这样你的remote连接重新连上fork仓库， 使用 git push等命令将更新提交后发出pull request!***



下面是我找的其他的发出pull request的方法，暂未试验过, 可以尝试一下：

![pull_request](./imgs/pull_request.png)