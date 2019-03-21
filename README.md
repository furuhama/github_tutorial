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

ターミナルは開きっぱなしで！

### ローカル環境の git リポジトリと GitHub の git リポジトリを紐づけてみよう

今はまだローカル環境の Rails アプリを GitHub 上のどの入れ物に送ればいいのかを設定してない状態

送り先を設定してあげよう

さてここで https://github.com/furuhama/github_tutorial#%E3%83%AA%E3%83%9D%E3%82%B8%E3%83%88%E3%83%AA%E3%81%AB%E5%90%8D%E5%89%8D%E3%82%92%E3%81%A4%E3%81%91%E3%82%88%E3%81%86 の最後に残しておいた画面に行ってみよう

![ss04](https://github.com/furuhama/github_tutorial/blob/master/img/ss04.png)

赤い四角で囲ってあるところに `https://github.com/~~~~~` みたいなアドレスが書いてあるね

それをコピペして、さっき開いていたターミナルで以下のコマンドを打ってみよう

```
git remote add origin <コピペしたアドレス>
```

これでローカル環境で、送り先の GitHub の入れ物が設定できた

### アクセストークンを取得しよう

このあといよいよ自分のコードを GitHub に送るとなった時に、そのための専用のパスワードを取得しないといけない

細かい理由はここでは説明を避けるけど、より安全な仕組みのために必要なこと、と思っておいてほしい

まずは https://github.com/settings/tokens にアクセスしてみよう

こんな画面になると思う

![ss05](https://github.com/furuhama/github_tutorial/blob/master/img/ss05.png)

右上の `Generate new token` を押したらパスワードを聞かれるから入力して先に進もう

そしたらこんな画面が出てくるはず！

![ss06](https://github.com/furuhama/github_tutorial/blob/master/img/ss06.png)

一番上の `repo` というところだけチェックをつけて、一番上の `Token description` に適当な名前をつけて(僕と同じで `local repository` とかでいいと思う!)

ページ一番下の `Generate token` をクリック

![ss07](https://github.com/furuhama/github_tutorial/blob/master/img/ss07.png)

すると元の画面に戻って、今回 GitHub が作ってくれた特別なパスワードが表示されているはず(下の写真だと赤い枠の中)

![ss08](https://github.com/furuhama/github_tutorial/blob/master/img/ss08.png)

このパスワードは一回しか表示されないから、ページを閉じる前にちゃんとどこかにメモしておこう

(間違って消しちゃったら、また https://github.com/settings/tokens にアクセスして作り直そう)

### ローカル環境の git リポジトリから GitHub の git リポジトリにファイルを反映させてみよう

ここまできたら実際にソースコードを GitHub に送ってみよう

細かい意味まではここでは説明しないけど、今までの設定がうまく行っていたら、以下のコマンドを上から順に打つとうまく行くはず！

```
git add .

git commit -am 'Initial commit'

git push origin master
```

そしたら Username とか Password とかを聞かれるから

自分の GitHub の ID と、さっき GitHub 上で作ったパスワードを入力しよう

```
Username for 'https://github.com': furuhama (<- ここは自分の GitHub ID を入れよう)
Password for 'https://furuhama@github.com': (<- 自分の GitHub のパスワードを入れよう)
```

上手くいったら

```
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 4 threads
Compressing objects: 100% (7/7), done.
Writing objects: 100% (7/7), 639.14 KiB | 15.59 MiB/s, done.
Total 7 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/~~~~~~~~~~~/~~~~~~~~.git
   7c7xdd1..dxcx4b2  master -> master
```

みたいなメッセージが表示されるはず。

そしたら GitHub の自分リポジトリのページに行ってみよう！自分のソースコードが見えるようになっている

### おわり

これで晴れて自分のソースコードを

### (番外編) GitHub のすごいところ

### 補足

難しい内容に触れないように書いたので、正確じゃない書き方をしているところもあるけど、まずは気にせずに GitHub を楽しく使えるようになろう！
