##01 CSSとはなにか？

* 概要  
\- ホームページ=HTML(構造的な文章) + CSS(見た目)  

* 必要となる知識  
\- HTML  

* ツール  
\- ブラウザ -Chorome  
\- テキストエディタ -Atom,sblimetext等  

* 範囲  
\- CSS 2.1  

* 仕様  
\- w3s(https://validator.w3.org/)で確認できる  

---

##02 はじめてのCSS

エディタで実際に書きました  

---

##03 セレクタとプロパティを理解しよう

* セレクタ: {プロパティ名: 値;}
* プロパティ
* \*: ユニバーサルセレクタ。全ての要素を選択する
* 要素セレクタ: p,h1,div
* idセレクタ
* classセレクタ

---

##04 もっとセレクタを使ってみよう

  セレクタ  
    a, b : 同じスタイルを複数のセレクタに適応する場合
    a b : aの下にある階層bを全て指定したスタイルにする
    a > b : aの直下にあるbにだけ指定したスタイルにする
    a + a : aの次にくるa要素にスタイルを適応する
    a.points : a要素であってpointsのクラスをもっているものにスタイルを適応する
    
    ---
    
    ##05 属性セレクタを使ってみよう
    
    属性セレクタ:  
      例:  
      a[title]: aタグの中にtitle属性があるものにスタイルを適応する  
      a[href="URL"]:aタグの中にURLがあるものにスタイルを適応する  
      a[class~="serach"]:aタグの中にcalss属性が含まれているものにスタイルを適応する  
      
      ---
      
      ##06 擬似クラスを使ってみよう
      
      疑似クラスタ:  
      例:  
      a[link]{color: violet}: リンクの色を変える  
      a[visited]{color: violet}: 訪問したリンクの色を変える  
      a[hover]{color: violet}: リンクにマウスが乗ったときに色を変える  
      a[active]{color: violet}: リンクをクリックしたときに色を変える  
      ※リンクに関する疑似クラスタは上記の順番で書く  
      
      ---
      
      ##07 擬似要素を使ってみよう
      
      疑似要素:ある要素の一部を指定する時に使う  
      p:first-line{color: violet}: 1行目にのみ適応する  
      p:first-letter{color: violet}: 一文字のみに適応する  
      p:before {  
        content: "";  
      }  
      p:after {  
      content: "";  
      }  
                    : ある要素の直前直後に付け加えた場合に使う  
                    
---

##08 セレクタの詳細度を理解しよう

詳細度:複数のセレクタがあった場合、どのセレクタが優先されるか  

(a) style=""  
(b) id  
(c) 属性/疑似クラスタ  
(d) 要素/疑似要素  

/*0,0,0,1*/  
a {color: skyblue;}  
/*0,0,1,1*/  
a.link {color: orange;}  
/*0,1,0,1*/  
a.search {color: skyblue;}  
※!importantを付けると優先順位が一番高くなる  

---

##09 プロパティの値を指定しよう

値  
- 長さ  
  - px: ピクセルで指定する  
  - em: 親要素の何倍かで指定する  
  - %: 親要素の何%かで指定する  
- 色  
  - 名前  
  - RGB  
    -Rea: 0-f / 00-ff / 0-255 / 0%-100%  
    -Green  
    -blue  

---

##10 ボックスモデルを理解しよう

width:幅  
height:高さ  
border:領域に枠線を付ける  
padding:borderと要素の内側にあるもの  
margin:borderと要素の外側にあるもの  
※heightは親要素の高さを明示的に示さないとならない  

---

##11 borderで境界線のスタイルを変えよう

border-color: 色  
border-width: 高さ  
border-style: スタイル(solid, dotted, dashed, double, inset, outset)  

一気に順不同活省略して指定出来る  
例: border: orange 4px dotted  

また、styleは上だけ右だけの様に指定出来る  
例: border-top: orange 4px dotted  

---

##12 paddingで余白を制御しよう

padding-top: 10px;  
padding-right: 10px;  
padding-left: 10px;  
padding-bottom: 10px;  

まとめて指定することも出来る  
プロパティで指定する数によって変わる

padding-:
  all
  1つの場合: 上下左右  
  2つの場合: top/bottom right/left  
  3つの場合: top right/left bottom  
  4つの場合: top right bottom left  
  
  例:  
  padding: 10px 20px 30px  
  この場合:topが10px,right/leftが20px,bottomが30px  
  
  ---
  
##13 marginとmarginの相殺を理解しよう
  
margin-top: 10px;  
margin-right: 10px;  
margin-left: 10px;  
margin-bottom: 10px;  

まとめて指定することも出来る  
プロパティで指定する数によって変わる

margin-:
  all
  1つの場合: 上下左右  
  2つの場合: top/bottom right/left  
  3つの場合: top right/left bottom  
  4つの場合: top right bottom left  
  
  ※上下ににブロックボックスが並んだ場合:marginは結合されて、大きい方marginになる
  
  ---
  
  ##14 文字に関するプロパティを使ってみよう
  
text
- color: orange; ← 色  
- font-size: 14px; ← 大きさ  
- font-family: Arial, Helvetica;  ← フォントの種類  
- font-weight: bold/normal; ←  太字にするかどうか  
- text-aligin: right/center/left; ←  行揃え  
- text-decoration: underline/line-through/none; ← 下線、打ち消し線、消す   

---

##15 list-styleでリストのスタイルを変えよう

list-style-type: disc/circle/square/decimal/lower-alpha ← リストの前にあるマーカーのスタイルを変える  
list-style-image ← 画像のファイル名を指定するとマーカを画像にしてくれる  
list-style-position: inside/outside ← マーカーをリストの中に入れることが出来る  
list-style ← 一気に指定出来る.順不同かつ省略可能  
※list-styleで画像を使った場合、list-style-typeは上書きされる  

---

##16 cursorでカーソルの形状を変えよう
- 
