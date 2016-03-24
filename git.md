####打patch
- 根据commit hash打patch：比如提交了两次，commit1和commit2，commit2是最近的一次提交，则git diff commit1 commit2 > diff.patch

####应用patch
> git apply diff.patch

> patch -p1 < diff.patch

####有时候新加文件有mp3等需要打patch的，按以下方式
**[使用git format-patch生成所需要的patch](http://blog.csdn.net/kevinx_xu/article/details/11660915):**
> git format-patch -s 1bbe3c8c197a35f79bfddaba099270a2e54ea9c7
please replace the hash code with your repo previous commit.
then you can find the patch under repo directory.
then mail your patch to configuration admin. 

- git format-patch -M master         // 当前分支所有超前master的提交
- git format-patch -s 4e16                // 某次提交以后的所有patch, --4e16指的是SHA1 ID
- git format-patch -1                     //  单次提交
- git format-patch -3                    // 从master往前3个提交的内容，可修改为你想要的数值
- git format-patch –n 07fe            // -n指patch数，07fe对应提交的名称, 某次提交（含）之前的几次提交
- git format-patch -s --root origin     // 从origin到指定提交的所有patch

**应用patch：**
- 先检查patch文件：# git apply --stat newpatch.patch
- 检查能否应用成功：# git apply --check  newpatch.patch
- 打补丁：# git am --signoff < newpatch.patch(使用-s或--signoff选项，可以commit信息中加入Signed-off-by信息)或git am

####不改变ChangeId，追加commit
  - git add .
  - git commit --amend -m"..."

####[Git处理大文件](https://git-lfs.github.com)
- brew install git-lfs
- git lfs install
- git lfs track "*.dmg"
- 上传.gitattributes文件
