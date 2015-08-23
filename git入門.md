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
    :woで保存
$ cat name.html ← name.htmlの中身を見る  
$ git add name.html ← 作業ディレクトリからステージングエリアに上げる  
$ git commit ← ステージングエリアからリポジトリに上げる(エディットが立ち上がるので覚えやすいメッセージを入力する)  
$ git log ← logを見る  

---

##05 gitのログを見てみよう

1. $ git logでlog表示される(以下に表示された内容を上から説明)  
commit 数字の羅列 ← commitに付くIDのようなもの  
Auther: namae <email> ← commitした人  
Date ← commitした日時  
一番下に自分がつけたcommitメッセージ。多くなると分からなくなるのでなるべく分かりやすく  

2. $ git logのオプション  
$ git log --oneline ← コンパクトに見たい時に使う  
$ git log -p ← 変更された場所もみたい時に使う
※null≓何もない  
$ git log stat ← どこが変更されたかではなく、どのファイルが変更を加えたかを見れる

---

##06 現在の状態を把握しよう

$ ls ← ファイル,ディレクトリの情報を表示する    
$ git status ← ステージイングエリア,commitに上がっているかを教えてくれる  
$ git checkout -- name.html ← 変更したファイルを取り消す  
よく分からなくなったら$ git stausを使う  

---

##07 差分を確認しよう

$ git diff ← どこをどう変更されたか分からない時に使う。  

・ステージングエリアに上げていない場合  
$ git diff  
・ステージングエリアに上げている場合  
$ git diff --cached  

---

##08 gitでのファイルの操作

$ git add . ← 今のディレクトリより下にあるファイルを全てステージングエリアに上げる  
$ git rm name.html ← ファイルの削除(この場合、name.htmlを削除する)  
$ git mv name.html ← ファイルの移動  
※一度ステージングエリア,コミットに上げた後にLinuxのコマンド(rm,mv)を使うとgitで管理していたファイルが分からなくなるので注意    

---

##09 git管理に含めない設定について

$ vim .gitignore ← エディタが開き、*.logの用に入力すると、.logを除外出来る  
※gitignoreは置いた場所とその下の階層に適応される  

---

##10 直前のコミットを変更する

$ git commit -m "ライン2を追加" ← 一行ぐらいしかコメントを書かない場合に使う。""に文字を入れる    
$ git commint --amend ← 直前のコミットを編集出来る    

---

##11 過去のバージョンに戻ってみよう(1)

$ git reset --hard HEAD ← hardは作業ディレクトリもステージングエリアも戻したい時に使う。HEAD^を入力するとHEADの前のものをさす  
※HEADは戻したいcommitIDでも良い(HEADは先頭)

---

##12 過去のバージョンに戻ってみよう(2)

$ git reset --hard ORIG_HEAD ← ORIG_HEADに前回取り消されたHEADび情報が1つだけ入っている  
※commitされたものは基本的に全て保存されている。リセットの内容によっては作業ディレクトリやインデックスの内容が失われている場合があるので注意

---

##13 ブランチを使ってみよう

複数のバーションを作成することが出来る

$ git branch ← 別のバージョンを使いたい時に使う(分岐)  
$ git btanch (branch name) ← 新しいブランチを作る  
$ git checkout (branch name) ← ブランチを移動する  

---

##14 ブランチをマージしてみよう

$ git merge ← 別のブランチのファイルを他のブランチに反映させたいときに使う(masterブランチにhogeブランチを加えたい場合、masterブランチで$ git mergeを使う)  
$ git branch -d (branch name) ← ブランチを消したいときに使う  

---

##15 マージの衝突を解決してみよう(1)

$ git checkout -b branch ← ブランチを作り一気にその作ったブランチに移動する  

マージさせたいブランチのファイルが、元のブランチのファイルと同じだった場合、マージ時に衝突してしまう。次の回で解決する  

---

##16 マージの衝突を解決してみよう(2)

衝突した後、$ vim (file name)で開くと、

<<<<<<<HEAD  
line 1st  

=======  
line first  
>>>>>>>hogehoge  

と表示される。<<<<<<<HEADと>>>>>>>hogehogeで囲まれている部分がコンフリクトしていることを示している。(この場合、HEADとhogehogeのline 1stとline firstがコンフリクトしている)  

修正するには、<<<<<<<HEADと=======から>>>>>>>hogehogeの部分(line 1st以外)削除すれば良い   

※一人で作業している時でも、複数の人でやっている時でも、コンフリクトが起こることがあるので注意する

---

##17 タグを使ってみよう

コミットのIDに分かりやすい名前を付けられる  
バージョン1はこのコミット、のような主なコミットに別名を付ける  

$ git tag v1.0 ← 直近のコミットにタグを付ける  
$ git tag ← tagの一覧を表示  
※$ git show や& git resetなどでIDを指定するとき、設定したtagを使える  










