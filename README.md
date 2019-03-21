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

### そもそも GitHub って...？

GitHub はネット上に自分の書いたコードを公開できるサービス

他の人と簡単にコードを見せ合ったり、こう書いたらもっと良くなるんじゃないの？みたいな話ができる場所

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

リポジトリには好きな名前をつけよう！(もう自分で Rails アプリに名前を付けていたらそれがいいと思う！)

名前を入れたら、緑色になった `Create Repository` をクリックすれば OK

![ss03](https://github.com/furuhama/github_tutorial/blob/master/img/ss03.png)

このあとのステップで使うからこのページは開いておこう

### ローカル環境の Rails アプリで git が使えるようにしよう

ここまでで GitHub 上に、自分の書いた Rails アプリを置くための場所はできた。

次はローカル環境(自分の PC) にある Rails のコードを、 GitHub に送るための準備をしよう

#### Rails アプリのルートディレクトリに行く

ターミナルを開いて Rails アプリがあるディレクトリに行こう

`app` とか `bin` とか `config` とかがあるディレクトリに行けばおっけー

そこで以下のコマンドを打ってみよう

```
git init
```

うまくいくと

```
Initialized empty Git repository in ~~~~
```

みたいなメッセージが表示されるはず。そしたら準備 ok


========== ここまで書いた、あとは途中 ==========


### ローカル環境の git リポジトリと GitHub の git リポジトリを紐づけてみよう

今はまだローカル環境の Rails アプリを GitHub 上のどの入れ物に送ればいいのかを設定してない状態

送り先を設定してあげよう

```
git remote add origin ~~~
```

### ローカル環境の git リポジトリから GitHub の git リポジトリにファイルを反映させてみよう

```
$ git push origin master
Username for 'https://github.com': furuhama (<- ここは自分の GitHub ID を入れよう)
Password for 'https://furuhama@github.com': (<- 自分の GitHub のパスワードを入れよう)
```

### (番外編) GitHub のすごいところ

### 補足

難しい内容に触れないように書いたので、正確じゃない書き方をしているところもあるけど、まずは気にせずに GitHub を楽しく使えるようになろう！
