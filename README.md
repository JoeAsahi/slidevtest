# slidevtest

1つのGithub Actionsで複数のslidevをデプロイできるかのテスト

 - docs : ビルドされたスライドが格納されてPagesで公開される
 - slide01 : 各スライド毎にディレクトリを作って格納する
 - slide02
 - ...

monorepo形式なのでスライドが多くなってきたら[sparse-checkout](https://git-scm.com/docs/git-sparse-checkout)とかすると良いかも？

```
git clone --filter=blob:none --no-checkout https://github.com/JoeAsahi/slidevtest.git
cd slidevtest
git sparse-checkout init --cone
git sparse-checkout add <チェックアウトしたいディレクトリ>
git checkout main
```

@slidev/cliをインストールするのではなく、
初期作成時：npm init slidev
更新時：チェックアウト直後に、そのディレクトリでnpm install
を実行し、
npm run dev
で実行する方が良い
※slidev/cliだとテーマを変えた時にpackage.jsonに反映されない
