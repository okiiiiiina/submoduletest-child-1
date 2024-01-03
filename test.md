親のローカルにリモートリポジトリを追加して「git add」する前に、child-1のリポジトリを親のサブモジュールとして追加。
親のリポジトリにindexされていないため、エラーは出ずにサブモジュールとして追加される。

修正反映の確認
parentプロジェクトファイルをvscodeで開く
D:child-1 test/1 ブランチを作成
D:child-1 ファイルの変更を行う
D:parent  git status => コミットされていないファイルとして上がってくる
```
On branch master
Your branch is up to date with 'origin/master'.

// コミットされていない変更があります。これは、ワーキングディレクトリで修正されたファイルがあることを示しています。
Changes not staged for commit: 
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
  (commit or discard the untracked or modified content in submodules)
        modified:   child-1 (modified content)

no changes added to commit (use "git add" and/or "git commit -a")
```
D:parent  git add .
D:parent  git status => ステージングはされない。
D:child-1 git add .
D:parent  git status => ステージングされている。

結論
サブモジュール追加したディレクトリでの修正は親ではaddできない


