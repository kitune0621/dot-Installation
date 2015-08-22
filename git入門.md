## 01 gitとは何か

・バージョン管理システム

####公式サイト
http://git-scm.com/

####必要な知識
・Linuxのコマンド
・vim

####環境
Linuxのローカル開発環境 git

---

## 02 バージョン管理の流れを理解しよう

1. 作業ディレクトリ：ファイルを作ったり修正したりする場所

2. ステージングエリア(インデックス)：作業経過のようなものをここに保存出来る。

3. リポジトリ：ある程度のまとまりになったらここに保存する
※・ローカルリポジトリ：一人で作業する時に使う
　・リモートリポジトリ：webやネットワーク上にソースコードを公開し、複数人でサービスを作る時に使う。

---

## 03 gitを設定しよう

gitはデータを保存する時、名前とemailを書く。

$ git config --grobal user.name "kitune" ← 名前
$ git config --grobal user.email "kitune@dotinstall.com" ← email
$ git config --grobal color.ui true ← メッセージを色分け
$ git config -l ← 設定の一覧
$ git config --help(git help config) ← マニュアル表示
$ q ← 閉じる

---

##04 初めてのコミットをしてみよう

$ pwd ← 現在いる場所を表示する
$ mkdir "filename" ← ディレクトリを作成する
$ cd "filename" ← ディレクトリを移動する
$ git init ← ディレクトリをgitで使うという宣言
$ vim name.html ← name.htmlというファイルを作成
$ cat name.html ← name.htmlの中身を見る
$ git add name.html ← 作業ディレクトリからステージングエリアに上げる
$ git commit ← ステージングエリアからリポジトリに上げる(エディットが立ち上がるので覚えやすいメッセージを入力する)
$ git log ← logを見る

---

##05 gitのログを見てみよう




