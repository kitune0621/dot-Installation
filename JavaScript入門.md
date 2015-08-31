##01 JavaScriptとはなにか？

概要  
 - ブラウザに実装されているスクリプト言語  
 - 動きのあるウェブサイト  
 - X Java  

リファレンス  
 - MDN(https://developer.mozilla.org/ja/docs/Web/JavaScript)  
必要となる知識  
 - HTML  
 - CSS  
必要となるツール  
 - ブラウザ  
 -テキストエディタ  

---

##02 はじめてのJavaScript

･<script></script>でくくる    
･console.log("HelloWorld");でコンソールにHelloWorldを表示する  
･コメントは、複数行は/*コメント*/、1行は//  
･文の終わりは;で区切る  
･<script src="name.js"></script>で外部ファイルを指定する  

---

##03 変数を使ってみよう  

･変数:データに付けるラベル  
  - var msg; ← msgという変数   
  - msg = "HalloWorld" ← msgにHalloWorldを代入する.=は右辺を左辺に代入するという意味  
  - 宣言と代入を一気に行うことも可能  
･データ型  
  - 文字列   
  - 数値  
  - 真偽値(true / false)  
  - オブジェクト  
   - 配列  
   - 関数  
   - 組み込みオブジェクト  
  - undefined 定義されていない  
  - null 何もない  
  
---

##04 数値を使ってみよう

･数値  
 - 整数  
 - 小数点  
 - 負  
･演算子  
 - +,-,*,-  
 - += 代入を伴う演算子  
 - ++,-- 単項演算子  

---

##05 文字列を使ってみよう  

･文字列  
 - ''などを文字として表示したい場合は,\と付ける  
 - \nは改行,\tはタブ  
･演算子  
 - 文字列を連結したい場合は+をつかう.  
 - 数字を文字列とした場合、文字列との連結になるので注意する(例:s = "5" + 5 結果55)  
 
 ---
 
 ##06 if文を使ってみよう

･条件分岐  
 - if(条件){    
      真    
   } else {    
      偽    
   } else if {  
      それ以外    
   }  
･ 比較演算子  
 - > <: 大小比較  
 - >= <=: 以上,以下  
 - ===: 等しい  
 - !==: 等しくない  
･ 論理演算子  
 - AND &&  
 - OR ||  
 - NOT !  

---

##07 真偽値と三項演算子を使お

･ 真偽値  
  - 文字列: 空文字以外だったらtrue  
  - 数値: 0 か NaN 以外だったらtrue  
  - teue /false  
  - object: null 以外だったらtrue  
  - undefined, null -> false  
  
･ 参考演算子  
  - ある条件下において,if else文を書き換えることが出来る構文  
  
---

##08 switch文を使ってみよう

･条件分岐  
  - switch文  
  例:  
    
  var = "red"  
  switch (signal) {  
    case "red":  
      console.log("stop!");  
      break;  
    case "blue":  
    case "green":  
      console.log("go!");  
      break;  
    case "yellow":  
      console.log("slow down!");  
      break;  
  }  
  
  
 
   
   







