##01 HTMLとはなにか

* 概要  
\- ホームページを作成する  
\- Hyper Text Markup Languageの略  
\- HTML(構造的な文章) + CSS(見た目)  
* 範囲  
\- THML5  
* 仕様  
\- M3C(https://validator.w3.org/)のサイトで仕様を確認できる  
※全ての機能が全てのブラウザで使えるとは限らない。確認したい場合はcaniuse(http://caniuse.com/#)で確認できる  

---

##02 必要なツールを用意しよう

ツール  
1. ブラウザ - Chorome  
2. テキストエディタ - Atom  
3. フォント - Ricty Diminished(0とOが見やすかったり、全角半角が見分けやすい)  

---

##03 タグと属性を理解しよう

用語  
1. タグ  
<タグ>文章</タグ>  
2. 属性  
<タグ 属性名=値 属性名=値...>文章</タグ>  
※情報や部品を配置したい場合は<タグ>のみで1つだけタグを書くもともある  
例:<p \class="message">Hello World</p>  

用語を抑えることがHTMLをマスターするコツ

##04 はじめてのHTML

･タグを入れ子コードにする  
･タグを入れ子にする際は、字下げ(インデント)をよくする。字下げはTabキーまたはスペースキーで行う  
･ファイルを保存する場合は、半角英数字で書く
・一般的に、初めに表示されるファイルは｢index.html｣という名前にする

---

##05 meta linkタグを使って見よう

\<!DCOTYPE hrml> ← HTMLで文章を書くときの宣言的なもの  
\<heml lang="jp"> ← 基本的にはhtmlタグでくくり、lang(言語)を指定する  
\<head> ← 文章自体の情報を書く  
\<body> ← 本文などを書く  
\<title> ← ブラウザで表示した際に、タブなどに表示される文字列  
\<meta charset="utf8"> ← このページの文字コードを指定する。この場合は、utf8に設定する。(chrsetの綴りを間違えたりすると文字化けが起こる  
\<meta name="description" content="初めてのHTMLの文章です"> ← 文章の説明。検索に引っかかるようにする  
\<mlink rel="shortcut icon" href="favicon.jpg" > ← favicon(タブなどで表示されるアイコン)。relでshortcutと書き、hrefでアイコン名を書く。

---

##06 styleタグを使って見よう

\<style> ← 文章の見た目を規定するためのCSSを書くことが出来るタグ  
例:
\<style>  
body {background: skyblue;}  
\</style>  

\styleは書いていると長くなることがあるので、その場合は別のファイル(css)に分ける  
cssファイルの指定方法は  
\<link rel="stylesheet" href="name.css">  
でcssが呼び出される

\<!-- コメント --> ← 動作に関係ないメモ書きを書くことが出来る。

---

##07 is,class,style属性を使って見よう

全てのタグに付けられる属性をグローバル属性という  

グローバル属性  
･id:ひとつしかない要素(ページ内でジャンプしたり、他のプログラムがこの要素を取得したりするときに使う)  
･class:複数ある要素  
･style:スタイルを直接指定  

---

##08 セクションについて理解しよう

文章のアウトラインと意識することが重要  

header:ヘッダーを指定する。  
footer:フッターを指定する。  
nav:ナビゲーションに関するタグ。グローバルメニューやサイドメニューなど    
article:独立しているコンテンツ(ニュース記事やブログエントリーなど)  
aside:副次的なコンテンツ(補足情報や広告など)  
section:それ以外の情報のかたま塊(なんらかの見出しを付けて整理したいときに使う)  
h1 - h6:セクションに付ける見出し。h1が一番大きく、h6が最も小さい  

---

##09 アウトラインを意識してみよう

エディタで実際に作りました  

---

##10 h1-h6タグで見出しを付けよう

エディタで実際に作りました  

---

##11 p､hr､pre､blockquote､divを使かう

p:段落(パラグラフ)  
hr:水平線(話題転換をしたい時などに使う)  
pre:改行や字下げを保持(AAなどで使う)  
blockqupte:引用  
div:レイアウトや見た目を規定するCSSと組み合わせてスタイリング目的でグルーピングするときに使う  

---

##12 ol､ul､li､dl､dt､ddでリストを作ろう

リスト ← 情報をグループ化する  

ol (ordered list) / ul (unorder list) / li (list item)  
dl (definition list) / dt (definition term) / dd (definition description)  

---

##13 strong､br､spanを使ってみよう

strong
br
span












