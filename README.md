## GitHub チュートリアル

### はじめに

#### 目標

開発中の Rails アプリを GitHub で公開できるようになる

#### やること

- GitHub の簡単な使い方
- git の簡単なコマンド

#### やらないこと

- git の詳細な仕組み
  - branch
  - fork
  - clone
  - 通信の秘匿性の担保
  - commit の操作

### GitHub で git リポジトリを作ってみよう

まずは GitHub 上に、自分の Rails アプリを公開するための入れ物を作ろう

この入れ物のことをこのドキュメントでは `リポジトリ` と呼ぶよ

#### リポジトリ作成画面へ行く

https://github.com にアクセス

画面右上の `+` ボタンを押すと `New Repository` というメニューが出てくるのでそれをクリック

![ss01](https://github.com/furuhama/github_tutorial/blob/master/img/ss01.png)

(もしくは最初から https://github.com/new にアクセスしてもいい)

#### リポジトリに名前をつけよう

リポジトリに名前をつけて作成してみよう

![ss02](https://github.com/furuhama/github_tutorial/blob/master/img/ss02.png)

リポジトリには好きな名前をつけよう！(もう名前が付いていたらそれがいいと思う！)

名前を入れたら、緑色になった `Create Repository` をクリックすれば OK

### ローカル環境に git リポジトリを作ってみよう

### ローカル環境の git リポジトリと GitHub の git リポジトリを紐づけてみよう

### ローカル環境の git リポジトリから GitHub の git リポジトリにファイルを反映させてみよう

```
$ git push origin master
Username for 'https://github.com': furuhama (<- ここは自分の GitHub ID を入れよう)
Password for 'https://furuhama@github.com': (<- 自分の GitHub のパスワードを入れよう)
```

### (番外編) GitHub のすごいところ

