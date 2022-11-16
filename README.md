# slidevtest

1つのGithub Actionsで複数のslidevをデプロイできるかのテスト

 - docs : ビルドされたスライドが格納されてPagesで公開される
 - slide01 : 各スライド毎にディレクトリを作って格納する
 - slide02
 - ...

monorepo形式なのでスライドが多くなってきたら[sparse-checkout](https://git-scm.com/docs/git-sparse-checkout)とかすると良いかも？

```
git clone --filter=blob:none --no-checkout https://github.com/JoeAsahi/slidevtest.git
git sparse-checkout init --cone
git sparse-checkout add <チェックアウトしたいディレクトリ>
git checkout main
```
