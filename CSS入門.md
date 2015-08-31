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

cursor
- .help{ cursor: help; } ← helpカーソルを表示する  
- .dargme{ cursor: move; } ← moveカーソルを表示する  
- .clickme{ cursor: pointer; } ← ponterカーソルを表示する  
- .smail{ cursor: url('URL'); } ← URLで指定した画像を表示する  

---

##17 backgroundで背景スタイルを変えよう

background-color: silver; ← 背景の色を変える  
background-image: url('bg.jpg') ← 背景の画像を指定する  
background-repeat: no-repeat ← 画像を一度だけ表示する(敷き詰められない)  
/*background-repeat: repeat-x*/ ← x方向にだけ表示する  
background-postion: 10px 10px ← 画像の位置を指定する  
/*background-postion: top center*/ ← 言葉で指定も可能  
background-attachment: scroll ← スクロールに追随する  
/*background-attachment: fixed*/ ← 動かない  
backgroundプロパティで順不同かつ省略して指定出来る  

---

##18 displayで要素の配置方法を変えよう

display
ブロックボックス ← 下に積み重なって配置されていること  
ブロックレベル要素 ← h1やpのこと  
インラインボックス ← 左に詰められて配置されていること  
インラインレベル要素 ← spanタグやaタグのこと  

display:  
  - block;  
  - inline; ← 左に詰める(幅と高さの指定が無効になる)  
  - list-item;  
  - inline-block; ← 左に詰める(幅と高さを指定できる)  
  - none; ← 何も表示しない  

---

##19 positionで位置を調整してみよう

postion:  
  - static; ← 初期値  
  - relative; ← staticの位置からずらして表示した場合に使う(top,bottom,right,leftを使う)  
  - fixed; ← スクロールしても位置を固定しておきたいときに使う    
  - absolute; ← 親要素のpostionによって変わる.box3をabsoluteのした場合、box2が親となる.box2で何も指定していない,もしくはstaticの場合、画面の左上端が基準点となる.親要素を基準点としたい場合は,box2でrelativeを使う     

---

##20 z-index､overflowを理解しよう
  
z-index
  - 要素の重なり順を指定する  
  - 後ろに書いたものほど上になる  
  - 値が大きいほど上になる  
overflow ← コンテンツが幅と高さを超えて存在するときに使う  
  - visible ← そのまま表示する  
  - hidden ← はみ出た部分を非表示にする  
  - scroll ← スクロール領域を作る   
 
---

##21 line-height､vertical-alignを理解しよう

line-height ← ボックスモデルにある行モデルを指定する(倍で指定する場合は数字のみ書く.1.5倍であれば1.5)  
vertical-align ← 文章の途中や前後に画像などのインラインレベル要素を表示した場合に使う.デフォルト値は
ベースライン,親要素のフォントのベースラインに揃えられる.(top,bottom,middle.?px,?emで指定する)  

---

##22 float､clearを使ってみよう

float ← 指定した要素を通常の配置の流れから切り離し、左右に寄せるためのプロパティ(行ボックスの中身はフロートをさけて配置する).フロートされた要素はブロックボックスを生成するため、幅を指定するのが決まり.  
clear ← フロートを解除するプロパティ(ブロックレベル要素にしか適応出来ない)  








