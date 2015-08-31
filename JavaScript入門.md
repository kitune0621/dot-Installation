##01 JavaScriptとはなにか？

概要  
 \- ブラウザに実装されているスクリプト言語  
 \- 動きのあるウェブサイト  
 \- X Java  

リファレンス  
 \- MDN(https://developer.mozilla.org/ja/docs/Web/JavaScript)  
必要となる知識  
 \- HTML  
 \- CSS  
必要となるツール  
 \- ブラウザ  
 \- テキストエディタ  

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
  \- var msg; ← msgという変数   
  \- msg = "HalloWorld" ← msgにHalloWorldを代入する.=は右辺を左辺に代入するという意味  
  \- 宣言と代入を一気に行うことも可能  
･データ型  
  \- 文字列   
  \- 数値  
  \- 真偽値(true / false)  
  \- オブジェクト  
   \- 配列  
   \- 関数  
   \- 組み込みオブジェクト  
  \- undefined 定義されていない  
  \- null 何もない  
  
---

##04 数値を使ってみよう

･数値  
 \- 整数  
 \- 小数点  
 \- 負  
･演算子  
 \- +,-,*,-  
 \- += 代入を伴う演算子  
 \- ++,-- 単項演算子  

---

##05 文字列を使ってみよう  

･文字列  
 \- ''などを文字として表示したい場合は,\と付ける  
 \- \nは改行,\tはタブ  
･\演算子  
 - 文字列を連結したい場合は+をつかう.  
 \- 数字を文字列とした場合、文字列との連結になるので注意する(例:s = "5" + 5 結果55)  
 
 ---
 
 ##06 if文を使ってみよう

･条件分岐  
 \- if(条件){    
      真    
   } else {    
      偽    
   } else if {  
      それ以外    
   }  
･ 比較演算子  
 \- > <: 大小比較  
 \- >= <=: 以上,以下  
 \- ===: 等しい  
 \- !==: 等しくない  
･ 論理演算子  
 \- AND &&  
 \- OR ||  
 \- NOT !  

---

##07 真偽値と三項演算子を使お

･ 真偽値  
  \- 文字列: 空文字以外だったらtrue  
  \- 数値: 0 か NaN 以外だったらtrue  
  \- teue /false  
  \- object: null 以外だったらtrue  
  \- undefined, null -> false  
  
･ 参考演算子  
  \- ある条件下において,if else文を書き換えることが出来る構文  
  
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

---

##09 while､do ... whileを使ってみよう

while文 ← 先に条件判定がされる  
do ... while文 ← 最後に条件判定がされる  

---

##10 for文を使ってみよう

for文
 - 条件でループさせる  
 - break;  
 - cotinue;  

for (var i = 0; i < 10; i++){  
   if (i === 5){  
      break; ← ループ処理を抜ける  
      continue; ← ループ処理を1回スキップする  
   }  
}  

---

##11 alert､confirm､promptを使おう

alert ← ダイヤログボックスを出す.情報を提示したいときに使う     
confirm ← okとキャンセルボタンのあるダイヤログをだす.okを押すとtrue,キャンセルを押すとfalseを返す  
prompt ← ユーザーから情報を受け取るときに使う.何かが入力されたらその値が返り,何も入力されなければnullが返る  初期値を指定しておくことも可能  

---

##12 関数を使ってみよう

関数: 複数の処理  
 function 関数名(引数){  
    処理  
    retrun 返り値  
 }
 
---

##13 ローカル変数を使おう
 
 ･ 関数の中で変数はローカル変数と呼ばれ,その関数の中でしか有効ではない    
 ･ 関数もデータ型なので変数に入れることも可能.無名関数や匿名関数と呼ばれる  
 
---

##14 即時関数を使ってみよう

即時関数: 定義したあとすぐに呼び出したいときに使う.   
例1:  
(function(name){  
    console.log("hello");    
})();    
  
引数も取る事も可能  
例2:  
(function Hello(name){  
    console.log("hello" + name);   
})("Tom");    

---

##15 setInterval､setTimeoutを使おう

setInterval: ある一定時間ごとにある処理を繰り返す.前の処理が終わったかどうかを気にしない  
setTimeout: ある一定時間後にある処理を1回繰り返す.前の処理が終わったかどうかを考慮する  

settimeoutを繰り返し処理にするには、functionの外に関数をつける  
止めたい場合は,if構文を使う  

---

##16 配列を使ってみよう

配列: グループ化されたデータ  
var score = [100, 300, 500]  
console.log(score[1]) //添字0,1,...  
score[2] = 400;  
var m = [  
    [1, 2, 3]  
    [4, 5, 6]  
];  
console.log(m[1][1]); //この場合5  

---

##17 オブジェクトを使ってみよう

オブジェクト:名前と値  
 var user = {  
     email: "kita@gmail.com",  //プロパティ
     score: 80,  
 };  
 console.log(user["email"])  
 console.log(user.email)   
 cosole.score = 100 //書き換えることも可能  
 
 ---
 
 ##18 メソッドを使ってみよう
 
 var user = {  
   email: "kita@gmail.com",  //プロパティ  
   score: 80,    
   greet: function(name) { //メソッド  
        console.log("hello" + name + "from" + this.email); //thisは自分がいるオブジェクトを参照する  
   }  
 };  
 
 ---
 
 ##19 Stringオブジェクトを使おう
 
 組み込みオブジェクト  
  - String  
  - Array  
  - Math  
  - Date  

var s = new String("kita")  //文字列リテラル    
cosole.log(s.length); //文字数を返す   
cosole.log(s.replace("t", "T"));  //置換をする  
cosole.log(s.substr(1, 3));  //部分文字列を返す  

---

##20 Arrayオブジェクトを使おう

var s = new Array(100, 200, 300)  
cosole.log(s.length);  //要素の個数を返す  
// unshift -> array <- push  
// shift   <- array -> pop  
a.push(500);  
console.log(a);  
a.splice(1, 2);  //第一引数にどこに追加削除するか指定する.第二引数はそこまで追加削除するか指定する
console.log(a)  

##21 Math､Dateオブジェクトを使おう

console.log(Math.PI);  //円周率  
console.log(Math.ceil);  //切り上げ  
console.log(Math.floor);  //切り捨て  
console.log(Math.round);  //四捨五入  
console.log(Math.random());  //ランダム値を生成  

var d = new Date();  //現在の時刻を取得  
var d = new Date(2015, 1, 11, 10, 20, 30)  //特定時刻の取得※jsの場合は付は0から始まる.2月は1  
console.log(d.getFullYear());  //年を取得  
console.log(d.getMonth());  //月を取得  
console.log(d.getFullYear());  基準日(1970/1/1)からの経過ミリ秒を取得  

---

##22 DOMとは何か？

console.dir(window); // オブジェクトのプロパティを表示  
console.log(window.outerHeght); // windowの高さを示す  
window.location.href = "URL" //URLに飛ばす  
winodw.document - 今開いてるページ //今開いてるページをjsで操作し動的にページの一部を書き換えたり、要素を追加したりする  
document object model (DOM)  //命令がブラウザによってまちまち.  

##23 DOMを操作してみよう

<h1>見出し</h1>
\<p id="msg">こんにちは</p>
<script>
   var e = document.getElementById('msg');  
   e.textContent = 'hello';  //テキストを書き換える  
   e.style.color = 'red';  //色を変える  
   e.className = 'myStyle';  //スタイルを変える  
</script>  

新しくElementを追加する場合  
var greet = document.createElement('p'),  
    text = document.createTextNode('hello world');  
 document.body.appendChild(greed).appendChild(text);    
 
 ##24 イベントを設定してみよう  
 
 ページ内の要素にイベントを設定する  
 
<body>  
<h1>見出し</h1>  
\<p id="msg">こんにちは</p>  
<button id="add">Clike!</button>  


document.getElementById('add').addEventListener('Clike!', function(){  //Clikeを押すごとにHellowWorldを生成する   
    var greet = document.createElement('p'),    
        text = document.createTextNode('hello world');    
    document.body.appendChild(greed).appendChild(text);    
});  
</body>  



 




  
  
 
   
   







