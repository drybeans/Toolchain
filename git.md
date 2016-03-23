####打patch
- 根据commit hash打patch：比如提交了两次，commit1和commit2，commit2是最近的一次提交，则git diff commit1 commit2 > diff.patch

####不改变ChangeId，追加commit
>
  - git add .
  - git commit --amend -m"..."
