# 1.変数/定数

## 基本の Hello world!

どのプログラムもまずは、ここから。Hello world をデベロッパーツールのコンソールに表示させます。

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <h1>JavaScript基礎</h1>
    <script src="main.js"></script>
</body>
</html>
```

```
//devツールのコンソールでHello world!が確認できます。
console.log('Hello world!');
```

## 変数と型定義

変数とは、メモリ上に作られたデータを格納するための小さな箱のようなものです。
定数とは、1 度だけ宣言できるものもです。。
変数は`let`または`var`で宣言することができ、定数は`const`で宣言することができます。
`var`は再宣言、再代入が可能でバクを引き起こす可能性があり非推奨とされています。
`let`は再宣言が禁止されていますが、再代入は可能です。
`const`は、再宣言、再代入が禁止されています。

また、スコープの範囲も var, let, const によって変わります。
スコープとは、実行中のコードから参照できる範囲のことを言います。
var のスコープ範囲は関数スコープ内で、let, const はブロックスコープが範囲内です。
※関数スコープ・・・関数(function)ごとに作られるスコープ
※ブロックスコープ・・・ブロック({})ごとに作られるスコープ
| | var | let | const |
| ---- | ---- | ---- | ---- |
| 再宣言 | ◯ | × | × |
| 再代入 | ◯ | ◯ | × |
| スコープ | 関数 | ブロック | ブロック |

```
let message; //変数の宣言
message = 'Hello!'; // 変数の値の代入
console.log(message); // Hello!が出力されます。

message = 'こんにちは'; //値を再代入
console.log(message); //こんにちはが出力されます。
```

#### var の再宣言、再代入

※現在、let が推奨されていてあまり使うことはありません。

```
var a = 'おはようございます。';
a = 'こんにちは。'; //再代入ができます。
var a = '初めまして！'; //再宣言も可能です。
letの再宣言、再代入
//let.js

let b = 'おはようございます。';
b = 'こんにちは。';  //再代入ができます。
let b = '初めまして。';  //再宣言はできません。
```

#### const の再宣言、再代入

※厳密に言えば、const で宣言してもオブジェクトのキーは変更可能です。

```
const c = 'おはようございます。';
c = 'こんにちは。'; //再代入はできません。
const c = '初めまして。'; //再宣言もできません。
```

## データの型

データ型とはデータの分類のことです。プログラミング言語で値を適切にやり取りするにはさまざまなデータ型を扱う必要があります。
JavaScript には、6 つのプリミティブ(基本の)データ型があります。
どのプリミティブ型にもあてはまらないものがオブジェクトです。オブジェクトは複数の値を格納できます。
| データ型 | 概要 |
| ---- | ---- |
| Boolean | 真偽型：true / false のどちらかの値を表す。 |
| Null | null(値が入っていない状態を表す) |
| Undefined | 値が定義されていない状態 |
| String | 文字列型。1 連の文字のこと。 |
| Symbol | 一意で不変な値のデータ型。ECMAScript6 で新しく定義された型。 |
| Number | 数値型。数値を表す。 |

上記の 6 つのプリミティブデータ型に当てはまらないのがオブジェクト(Object)です。
オブジェクト型とは、キーと値のセットになった連想配列のようなものです。
JavaScript には連想配列がないため、そのような機能を使いたければオブジェクトを用いましょう。
また、オブジェクトの作成や呼び出しをする際に、２種類の書き方をすることができます。
配列のように`object['name']`とできるブラケット記法とドットで`object.name`のように繋ぐドット記法があります。それぞれルールが若干違うので、サンプルを見てみましょう。

### ドット記法

```
// 定義の仕方
let userData = {
    'name': 'John',
    'age': 25,
    'hobby': 'game'
};
// 代入
userData.age = 30;
userData.000 = 'わーい'; // 数字は指定できないからエラーになる
// 出力方法
let key = 'hobby';
console.log(userData.name); // John
console.log(userData.age); // 30
console.log(userData.key); // 変数かキーか識別できないためエラーになる
```

### ブラケット記法

```
// 定義の仕方
let userData = {
  name: "John",
  age: 25,
  hobby: "game",
};
// 代入
userData["age"] = 30;
userData["000"] = "わーい"; // エラーとならない
// 出力方法
let key = "hobby";
console.log(userData["name"]); // John
console.log(userData["age"]); // 30
console.log(userData[key]); // game 変数にキーを指定して呼び出すことができる
```

## 課題

#### 【JS_1-1】 変数に"Hello, World!"と文字列を代入し、出力してください。

#### 【JS_1-2】 以下の変数を条件の通り編集し、最後に出力してください。

```
var number = 100;
let userName = "Takashi";
```

（条件）

- var で定義した変数は変数の再定義を行う
- let で定義した変数は変数の再代入を行う

Object を定義しました。そこに対し、name, age, hobby というプロパティを追加し、
「name さんは age 歳で、趣味は hobby です」という文をコンソールに出力してください。

```
let userData = {};
```

（条件）

- ドット記法とブラケット記法それぞれで書くこと

---

# 2.四則演算

## 演算子

演算子には、 算術演算子・代入演算子・論理演算子・比較演算子があります。

### 算術演算子

| 演算子 | 説明         | 例                             |
| ------ | ------------ | ------------------------------ |
| +      | 加算演算子   | a + b 　　 a に b を足す       |
| -      | 減算演算子   | a - b 　　 a から b を引く     |
| \*     | 乗算演算子   | a \* b 　　 a と b をかける    |
| /      | 除算演算子   | a / b 　　 a を b で割る       |
| %      | 剰余算演算子 | a % b 　　 a を B で割った余り |

### 代入演算子

| 演算子 | 使用例                                          |
| ------ | ----------------------------------------------- |
| =      | a = b 　　 a に b を代入する                    |
| +=     | a += b 　　 a に b を足して、a に代入する       |
| -=     | a -= b 　　 a から b を引いて、a に代入する     |
| \*=    | a \*= b 　　 a に b を掛けて、a に代入する      |
| /=     | a /= b 　　 a を b で割って、a に代入する       |
| %=     | a %= b 　　 a を b で割った余りを、a に代入する |

### 論理演算子

論理演算子とは、左辺、右辺の二つを評価して論理値(true・false)を返します。
『&&』は最初に左辺の式が評価(処理)されます。左辺の評価が true で、右辺の結果も true の場合に true を返します。左辺が false の場合は、その時点で false を返します。
『| |』も『&&』と同じくまず左辺の式が評価されます。左辺が false の場合、右辺を評価し true の場合は true を返します。
左辺の時点で true の場合は、右辺は評価をせず true を返します。
演算子 説明
a && b 左側が実行され、true の場合右側を実行する
a | | b 左側が実行され、false の場合右側を実行する
!a 真偽地を反転させます。a が true の場合は false、false の場合に true を返します。
比較演算子は以下の通りです。
if 文の条件だとかでよく使われます。
| 演算子 | 使用例 |
| ---- | ---- |
| a == b | a と b が等しい |
| a === b | a と b が等しい（データ型まで判定） |
| a != b | a と b が等しくない |
| a !== b | a と b が等しくない（データ型まで判定） |
| a > b | a が b より大きい |
| a >= b | a が b 以上 |
| a < b | a が b より小さい |
| a <= b | a が b 以下 |

## 課　題

#### 【JS_2-1】以下の計算を行い、コンソールに出力してください。

- １５足す３１
- ２３引く９９
- ５１割る 17
- １９掛ける３１
- ３１９を９で割った時のあまり
- １２７割る１１の結果を四捨五入する
- １３２掛ける１１.２３の結果を少数点以下切り捨てする
- ２５０割る１０.２５の結果を少数第 2 位で切り上げする

### 頭の体操です。

#### 【JS_2-2】 以下の条件に従い、計算式を作成してください。

3, 4, 7, 8 を用いて「10」という結果を出力する。
1, 1, 5, 8 を用いて「10」という結果を出力する。

---

# 3.文字列操作

## 文字列の結合

文字列を連結させたい場合、JavaScript では「+」演算子を使用します。
join 関数でも連結できます。

```
//変数同士の連結
let str1 = "こんにちは";
let str2 = "太郎さん";

let str3 = str1 + str2;
//str1とsr2の文字列が連結され、こんにちは太郎さんと出力される。
console.log(str3);

//文字列と数値の連結
let tool = "ペン";
let word = 100 + "個の" + tool;
console.log(word); //100個のペンと出力される。

//join関数による文字列の連結
const words;
const words = ["red", "yellow", "blue", "green"];
const result = words.join("");
console.log(result); //redyellowbluegreenと出力される。
```

## 正規表現

正規表現とはテキストの中から特定のパターンや条件に合致する文字列を検索や抽出することができるものです。

パスワードを登録するときに「半角英数字を含む〇文字以上で入力してください」といった文言を見たことがあると思います。
これに使用されているのが正規表現です。

JavaScript で正規表現を扱う際は RegExp を用いるか/で囲う必要があります。

```
//リテラル記法
const regexp = /[A-Z][a-zA-Z]/;

//RegExpコントラクタ
const regexp = new RegExp([A - Z][a - zA - Z]);

// 正規表現を適用させる文字列
const target =
  "JavaScript and React are different. TypeScript is a great language.";

const regex = /[A-Z][a-zA-Z]+/g;
// matchメソッドを用いることで、文字列中から正規表現にマッチする文字列を取得できます。
console.log(target.match(regex)); // => [ 'JavaScript', 'React', 'TypeScript' ]
```

[A-Z]：最初の文字がアルファベットの大文字である

[a-zA-Z]+：小文字と大文字のアルファベットを含む。＋は 1 回以上の繰り返しを示す

/g：条件にマッチするすべてのパターンを検索する
→ 上記の正規表現はアルファベットの大文字で始まり、そのあとに小文字化大文字のアルファベットが 1 つ以上続く文字列を示しています。
正規表現の詳しい文法についてはこちらを参照してください
[正規表現とは](https://www.tohoho-web.com/ex/regexp.html)

## 課題

#### 【JS_3-1】 以下のように、改行を含めた文字をコンソールに出力してください。

※ プログラムは１行です。

```
こんにちは。
今日はいい天気ですね。
明日お出かけしませんか？
```

#### 【JS_3-2】以下のコードで、文字列は数値に、数値は文字列に変換し、最後に型を確認できるような出力を行ってください。

```
let number = 123456;
let string = "789098";
```

#### 【JS_3-3】 以下の文で、「autumn」を「AUTUMN」に変換し、出力してください。

```
let text = "株式会社autumnです";
```

#### 【JS_3-4】 以下で定義する変数には、エクセルのファイルパスが格納されています。ここから、ファイル名だけを抽出してください。

```
let filePath = "user/document/excel/社員総会出席者リスト.xlsx";

// 最終的な出力
console.log(fileName);
```

---

# 4.配列操作

## 配列

配列というのは『連番が付けられた変数の集合体』のことです。配列を使うことで複数の値を 1 つの変数で保管・管理することができます。

```
var arr = ["Red", "Green", "Blue"];
console.log(arr);                     // => ["Red", "Green", "Blue"]
console.log(arr[0]);                  // => "Red"
console.log(arr[1]);                  // => "Green"
console.log(arr[2]); // => "Blue"
```

以下のようにして多次元の配列も扱うことができます。

```
let userData = [
  ['Yamada', 28, 'Tokyo'],
  ['Suzuki', 35, 'Fukuoka'],
  ['Honda', 24, 'Sendai']
];

let user1 = userData[0];
console.log(user1);// =>["Yamada", 28, "Tokyo"]が出力されます。
```

## 配列と forEach メソッド

forEach 関数は配列に格納されたデータをループ処理により、一気に処理したい時に使用します。
for 文より簡潔に記述することができます。
:::message alert
ループ処理は次の課題で扱うので軽く見る程度で大丈夫です
:::

```
const arry = [1, 2, 3, 4, 5];

//コールバック関数にfunctionを記述する。
arry.forEach(function(val) {
   console.log(val);
})

//出力結果
1
2
3
4
5

//アロー関数だとこのように記述できる。
arry.forEach(val => console.log(val));
```

### for-in について

for-in を使って、一般的なオブジェクトを処理する構文は次の通りです。
オブジェクトの中身を取り出したいときによく使用されます。

```
var object = {
    name: '田中',
    age: 20,
    hobby: 'サッカー'
};


for( var item in object ) {
    console.log( item );
}
実行結果
//変数「item」にオブジェクトのプロパティが1つずつ格納されている。
1. name
2. age
3. hobby
```

### 分割代入

分割代入とは、モダンな JavaScript で使われるようになりました。
配列の呼び出しに対して、簡潔なコードで参照することができます。早速サンプルを見てみましょう。

#### 通常の配列処理の場合

```
// 姓名の配列
let arr = ["John", "Smith"];

let firstName = arr[0];
let lastName = arr[1];

console.log(firstName); // John
console.log(lastName); // Smith
```

#### 分割代入を用いた場合

```
// 姓名の配列
let arr = ["John", "Smith"];
// 分割代入
let [firstName, surname] = arr;

console.log(firstName); // John
console.log(lastName); // Smith
```

サンプルは項目が 2 つしかないので良さが実感しにくいですが、配列のデータを一括で変数に格納することができます。

なお、左辺を直接オブジェクトにして一気に格納することも可能です。

```
let user = {};
[user.name, user.surname] = "John Smith".split(" ");

alert(user.name); // John
alert(user.surname); // Smith
```

また、この分割代入は値がなかった時のために初期値を設定することができます

```
// デフォルト値
let [name = "Guest", surname = "Anonymous"] = ["Julius"];

alert(name); // Julius (配列から)
alert(surname); // Anonymous (デフォルトが使用されました)
```

## foreach の key => value ができる！

強めに主張しましたが、分割代入のいいところの一つに、PHP でいう連想配列のループ処理の時に用いる foreach のような処理が簡単に実装できるということがあります。

#### PHP の記述

```
$userDataList = [
    'name' => 'Takashi',
    'age' => 25
];

foreach($userDataList as $key => $value){
    echo $key. '=>' . $value;
}
// 出力
// name => Takashi
// age => 25
```

#### 分割代入の記述

```
let user = {
  name: "John",
  age: 30,
};

// key-value のループ
for (let [key, value] of Object.entries(user)) {
  console.log(`${key}:${value}`); // name:John, then age:30
}
```

### Spread Operator

Spread Operator（スプレッド演算子）とは、　`...`　を用いた値の展開を行うオペレーターです。
配列に対して使うことができます（後ほどオブジェクトの場合も説明します）。具体的には以下のように使います。

#### 配列のスプレッド演算子

配列を呼び出す際に、`...配列の変数名`とすると中身を一気に取り出せます。

```
function func1(a, b, c) {
  console.log("func1", a, b, c);
}
let d = [1, 2, 3];
func1(...d); // => func1 1 2 3
// 配列の中に、...dを用いて配列を展開する
let d1 = [1, 2, 3];
let d2 = [0, ...d1, 4, 5];
console.log(d2); // => [ 0, 1, 2, 3, 4, 5 ]

// 分割代入で余った引数を...dで受け取る
let [a, b, ...d] = [1, 2, 3, 4, 5];
console.log(d); // => [ 3, 4, 5 ]

// 配列のコピーを行う（[...d]でコピーできる）
let d1 = [1, 2, 3];
let d2 = [...d1];
d2[1] = 10;
console.log("d1:", d1); // => [1, 2, 3] # 影響を受けない
```

#### オブジェクトのスプレッド演算子

##### 残りのプロパティを一気に受け付ける（...others のところ）

```
let person = {
  firstName: "Yohei",
  lastName: "Munesada",
  age: 31,
  city: "yokohama",
  favs: ["Ramen", "Tennis"],
};

const {
  firstName,
  lastName,
  ...others // age、city、favsを持つオブジェクトになる
} = person;

console.log("others:", others); // => others: { age: 31, city: 'yokohama', favs: [ 'Ramen', 'Tennis' ] }
```

##### オブジェクト内への展開（同じく...others のところ）

```
let other = { age: 31, city: "yokohama", favs: ["Ramen", "Tennis"] };

let person = {
  firstName: "Yuyu",
  ...others,
};
console.log("person:", person);
/*
    person: { firstName: 'Yuyu',
      age: 31,
      city: 'yokohama',
      favs: [ 'Ramen', 'Tennis' ] }
*/
```

## 配列メソッド

配列には多くのメソッドがあります。上記で記載した分割代入やスプレッド構文なども現場では頻繁に使われますが、最も多く登場するのはこの配列メソッドです。
その中でも特によく使う 3 つのメソッドを紹介します。
この他にも重要なメソッドは多く存在しますが、ここには載せきれないくらい多いため、勉強したい方は下記の URL を参考にしてください。

https://ja.javascript.info/array-methods

### map

`map()`メソッドは、与えられた関数を配列のすべての要素に対して呼び出し、その結果からなる新しい配列を生成するメソッドです。

#### 使用例

以下は、array という数字が格納された配列に対し、`map()`メソッドを用いた例です。<br>
まず、map の引数にはコールバック関数を入れます。（`(v, index) => v * 2`）<br>
このコールバック関数の内容で、どのように配列を処理するかを指定します。<br>
コールバック関数の第一引数（`v`）には、配列の要素が順番に格納されていきます。<br>
第二引数(`index`)は、現在のインデックス番号が入ります。<br>
result では array に入っている値を 2 倍した値を格納した新しい配列が生成され、result2 では、array2 のインデックス（array2 の要素数は２なので、0, 1 という順番でインデックス番号が振られていく）を 10 で掛けた値が格納されています。

```
const array = [1, 4, 9, 16];
const array2 = ["Taro", "Jiro"];

const result = array.map((v, index) => v * 2);
const result2 = array2.map((_, index) => index * 10);

console.log(result);
// 出力結果 [2, 8, 18, 32]
console.log(result2);
// 出力結果 [0, 10]
```

### filter

`filter()`メソッドは、与えられた関数をすべての要素に対して呼び出し、指定した条件に一致した要素からなる新しい配列を生成するメソッドです。

#### 使用例

以下は、words という文字列が格納された配列に対し、`filter()`メソッドを用いた例です。<br>
引数にコールバック関数を用いる点や、コールバック関数の引数については`map()`メソッドと同じです。<br>
このコールバック関数で行なっていることは、word に入る配列の要素が 6 文字以上であるかをテストしています。<br>
そして、テストをクリアした値だけ result という新しい配列に格納されています。

```
const words = [
  "spray",
  "limit",
  "elite",
  "exuberant",
  "destruction",
  "present",
];

const result = words.filter((word) => word.length > 6);

console.log(result);
// 出力結果 ["exuberant", "destruction", "present"]
```

### reduce

恐らく配列メソッドの中でも使い方が一番難しいメソッドです。<br>
配列を、オブジェクトにしたり、値の合算値を求めたりと、色々な形に加工できます。
ここでは、一番理解のしやすい配列のすべての要素の和をを返却する例を見て理解していきましょう。

#### 構文

以下は、`reduce()`メソッドの構文です。<br>
簡単に引数の役割を説明します。<br>

- `accumulator` – 前の関数呼び出しの結果で、初回は initial と等価です（initial が指定されている場合）
- `item` – 現在の配列の要素です。
- `index` – 現在の配列のインデックスです。
- `arr` – `reduce()`メソッドを使用している配列です。（使用頻度は少ないです）

```
const value = arr.reduce(function (accumulator, item, index, arr) {
  // ...
}, initial);
```

#### 使用例

以下は１行で配列の合計を取得する例です。<br>
2 つの引数だけを使用する`reduce()`の最も一般的なパターンです。<br>
処理の流れの詳細を見ていきましょう。<br>

1. 最初の実行で sum は initial 値(reduce の最後の引数)であり、 0 です。そして、current は最初の配列要素で 1 になります。従って、結果は 1 です。
2. ２回目の実行では、sum = 1 で、2 つ目の配列要素(2)をそれに足して返します。
3. ３回目の実行では、sum = 3 で、それに１つ要素を足します。それが続きます。
4. これらを続けた結果が result に格納され、15 という配列の合計値が出力されます。

```
const arr = [1, 2, 3, 4, 5];

const result = arr.reduce((sum, current) => sum + current, 0);

alert(result); // 15
```

## 課題

#### 【JS_4-1】 以下の配列からデータを取得し、サンプルのように出力してください。 なお、２種類の配列を作成したのでそれぞれ出力してください。

```
// サンプル
// ユーザー名 : 勇者ヨシヒコ
// メールアドレス : yoshihiko@yusha.com
// パスワード : YamadaTakayuki1020'

// 配列（１）
const array = ["勇者ヨシヒコ", "yoshihiko@yusha.com", "YamadaTakayuki1020"];

// 配列（２）
const array2 = {
  userName: "メレブ",
  mail: "merebu.merachin@yusha.com",
  password: "syakurena123",
};
```

#### 【JS_4-2】 以下に定義したオブジェクト型配列の中身をコメントアウトに従って処理をしてください。

```
let array = {
    name: 'takenaka',
    age: 25,
    adminFlag: false,
}

// nameを'Hanzo'にする

// １行で配列の出力をする
```

#### 【JS_4-3】 以下の配列に対し、「分割代入」を行い、指定した結果通り出力してください。

```
const userData = {
    name : "大槻",
    age : 24,
    hobby: "人間観察",
}
// 最終的な出力
// 私の名前は大槻、現在24歳！趣味は人間観察です。
```

#### 【JS_4-4】 1 つの配列を 3 つの配列に分けてください。 </br> ※ 出力を複数回に分けて構いません。

```
const array = ["a", "b", "c", "d", "e", "f"];
```

#### 【JS_4-5】 以下の配列を連結し、出力してください。

```
let array1 = ['こんにちは','おはよう','さようなら'];
let array2 = ['ヤッホー','わーい','バイバイ'];
```

#### 【JS_4-6】 分割代入と map を用いて、users をコメントアウトのような形になるように加工し、result という変数に格納し、出力してください。

```
const users = [
  {
    id: 1,
    detail: {
      name: 'Hoge',
      age: '22',
    }
  },
  {
    id: 2,
    detail: {
      name: 'Fuga',
      age: '25',
    }
  },
  {
    id: 3,
    detail: {
      name: 'Piyo',
      age: '33',
    }
  }
];

const result

// 出力結果
// [
//   {
//     id: 1,
//     name: 'Hoge',
//     age: '22',
//   },
//   {
//     id: 2,
//     name: 'Fuga',
//     age: '25',
//   },
//   {
//     id: 3,
//     name: 'Piyo',
//     age: '33',
//   },
// ]
```

#### 【JS_4-7】 分割代入と filter を用いて、items の中から price が 500 以上のものだけを取り出し、result という変数に格納し、出力してください。

```
const items = [
  {
    id: 1,
    price: 200
  },
  {
    id: 2,
    price: 500
  },
  {
    id: 3,
    price: 1000
  },
  {
    id: 4,
    price: 100
  },
  {
    id: 5,
    price: 700
  },
];

const result
```

#### 【JS_4-8】 分割代入と reduce を用いて、items という配列に格納された price の合計値を求めて result という変数に格納し、出力してください。

```
const items = [
  {
    id: 1,
    price: 100
  },
  {
    id: 2,
    price: 350
  },
  {
    id: 3,
    price: 650
  },
]

const result
```

#### 【JS_4-9】以下の多次元配列の各配列内で 20 以上の数値を 1 つだけ取得し、新しい配列 result に格納してください

```
const data = [
  [10, 23, 38],
  [45, 59, 26],
  [4, 18, 39],
];

console.log(result); // [23, 45, 39]
```

#### 【JS_4-10】下記 grade の連想配列から英語の点数だけの配列を作成し、点数を 2 倍にしてください。

```
const grade = [
  { name: "佐藤", subject: "math", score: 78 },
  { name: "高橋", subject: "English", score: 84 },
  { name: "鈴木", subject: "English", score: 90 },
  { name: "田中", subject: "English", score: 62 },
  { name: "山本", subject: "math", score: 54 },
  { name: "加藤", subject: "math", score: 88 },
  { name: "中村", subject: "English", score: 68 },
];
const result = 処理;

console.log(result); //[168, 180, 124, 136]
```

---

# 5.ループ処理

## ループの記述(for、for-of)

for 文などの繰り返し処理は、同じ処理を繰り返し行う構文です。
for 文は、括弧で囲みセミコロンで区切った 3 つの引数と、続いてループ内で実行される文 (ふつうはブロック文) から成るループを構成します。

```
let str = "";
//for ([初期化式]; [条件式]; [加算式])で表している。
for (let i = 0; i < 9; i++) {
  str = str + i;
}

//012345678が出力される。
console.log(str);
```

プロパティの「値」を取得するには、**オブジェクト[ プロパティ ]** の形で記述します。

```
for ( var item in object ) {
    //オブジェクト[ プロパティ ]の形で記述する。
    console.log( object[item] );
};
実行結果
1. 田中
2. 20
3. サッカー
```

for-of は主に配列や文字列などの繰り返し処理に使われています。
配列では値が 1 つずつ変数へ代入されているので、それぞれの値に対して処理を実行できます。

```
var array = [0, 1, 2, 3, 4, 5];

for(var item of array){

   console.log(item);

};

//実行結果
1. 0
2. 1
3. 2
4. 3
5. 4
6. 5
```

## 課題

#### 【JS_5-1】 for, while を用いて、それぞれ 1〜１００までの数字を出力してください。

#### 【JS_5-2】 ループ処理を用いて、a ~ zzz まで出力してみましょう。

※ エクセルのカラムをイメージすればわかりやすいと思います。
// アルファベットの配列

```
const alphabet = "abcdefghijklmnopqrstuvwxyz".split("");
```

---

# 6.条件分岐

## if 文と比較演算子

if 文は、「もし A ならば B を実行し、A でなければ C を実行」のように、条件や状況に応じて実行内容を変えたい場合に使用します。プログラミング言語には`true`（正）と`false'（誤）という概念があり、条件式と比較し true の場合と false の場合それぞれの処理を記述していきます。

```
if  (条件式) {
   条件式が真(true)の処理;
} else {
    条件式が偽(false)の処理;
}

//条件式を記述した用いたif文
var color = "青"
if(color == "青") {
  //変数colorに格納されている文字列と条件式が一致しているのでthis is trueの文字が出力される。
  console.log('this is true');
} else {
  console.log('this is false');
}

//複数の条件式を指定する場合は、else ifを記述します。
var orange = 100;
var apple = 120;

if(orange < apple){
 console.log('みかんの値段がりんごより安い');
} else if(orange == apple){
 console.log('みかんとりんごが同じ値段');
} else{
 console.log('みかんの値段がりんごより高い');
}

//論理演算子を使って一度に複数の条件を指定できます。
var color = "青";
if (color == "青" || color == "緑" ) {
   //colorが青または緑の場合に、trueを返します。
   console.log("進む")
} else {
   console.log("止まる")
}
```

## 三項演算子

三項演算子は JavaScript では唯一の、3 つのオペランドをとる演算子です。条件に続いて疑問符 (?)、そして条件が真値であった場合に実行する式、
コロン (:) が続き、条件が falsy であった場合に実行する式が最後に来ます。
この演算子は、IF - ELSE 文の省略形として利用することが可能で、3 つの値・式を必要とする特殊な演算子になります。

まず最初に、「IF 文」のおさらいをもう 1 度しておきましょう。

```
if (条件式) {
  //Trueの処理
} else {
  //Falseの処理
}
```

上記と同じコードを「三項演算子」で記述すると次のようになります。

```
条件式 ? Trueの処理 : Falseの処理
```

基本的な使い方

```
console.log( 15 > 6 ? true : false ); //実行結果 true
```

## Null 合体演算子

論理演算子の 1 つです。??（ハテナ 2 つ）で記述します。Null 合体演算子の??の左側が null または undefined の場合は右側の値を返し、そうでなければ左側の値を返します。
値や変数や関数などの後に??と記述することで使えます。null か undefined の場合だけ右側の値を返すので、初期値を設定したい場合に便利です。
null は値が空であることをあらわすオブジェクトで、undefined は宣言のみがおこなわれた変数の値や、return のない関数の戻り値です。

```
let message = userRequest ?? "nullかundefinedの場合はこのメッセージです";
```

```
returnの無い関数はundefinedを返します。関数呼び出しにNull合体演算子を使ってみます。
function noReturn(){
 console.log('noReturnが呼ばれました')
}

let message = noReturn() ?? 'nullかundefinedの場合はこのメッセージです';
```

変数 message には、null か undefined の場合はこのメッセージです、が格納されています。

```
let message = "" ?? "nullかundefinedの場合はこのメッセージです";
```

null と undefined 以外は左側が返されるので、変数 message には空文字が格納されています。

## 課題

#### 【JS_6-1】 以下の条件を満たす処理を実装してください。

くじ引きの配列 `loto`を用意しました。以下の条件に従い、処理を実装しましょう。
うまく条件分岐を用いて短いコードで実装するよう心がけてください。

- 配列 loto からランダムで取り出した値を変数に代入する
- 変数の値が null であった場合、代わりに 9 を代入する
- 変数が１の場合 => あたりと出力
- 変数が 0 の場合 => はずれと出力
- 変数が 9 の場合 => エラーが生じましたと出力

```
let loto = [0, 1, null];
// ランダムな数字を出力する
let key = Math.floor(Math.random() * 3);
```

#### 【JS_6-2】 トランプの配列を用意し、ランダムでカードを２枚引くプログラムを用意しました。その２枚の手札を使って以下の通り条件分岐を行って勝負をしてください。

#### 条件

自分より相手の数字が大きい場合 => 「残念！相手の方が大きいです」と出力
自分より相手の数が大きいが、差分が１の場合 => 「惜しい！相手の方が大きいです」と出力
自分より相手の数字が小さい場合 => 「やった！勝ちました！」と出力
自分より相手の数字が大きいが、差分が１の場合 => 「危ない！なんとか勝ちました」と出力
自分が Joker の場合 => 「おめでとうございます！圧勝です」と出力
相手が Joker の場合 => 「負けました。仕方がない」と出力
引き分けの場合 => 「引き分けです」と出力

```
const cardList = [
'A','2','3','4','5','6','7','8','9','10','J','Q','K','Joker'
];
let num1 = Math.floor(Math.random() * 14);
let num2 = Math.floor(Math.random() * 14);
let yourCard = cardList[num1];
let enemyCard = cardList[num2];
```

---

# 7.関数

## 関数の定義

関数とは、同じ処理をまとめて定義し、何度も使い回しができるかたちにしたものです。
関数を定義するときにまず必要となってくるのが、function（関数の意）です。それに続けて関数につける名前を書き、`{ }`のなかに処理を書きます。一番シンプルに書くとこのようになります。

```
function 関数名() {
  処理;
}
```

関数を呼び出すには 関数名(引数として渡す値) という記法で書きます。
引数とは、外部から受け渡される値となっています。
また、基本的に関数の結果は return で返すようにしましょう。return とは、値を返すことに加え、そこで処理を止めることができます。

```
// 関数の定義
function hello1(name) {
  var message = "Hello, " + name;
  return message;
  alert("メッセージ"); // これは実行されない
}
// 関数の呼び出し
var result1 = hello1("yamada"); //引数にyamadaを指定

// コンソールへ結果を出力
console.log(result1); //Hello, yamadaが出力される。
```

### 名前付き引数

関数の引数は複数取ることができるのですが、あまり数が多いとふと順番を忘れてしまいます。
関数の引数は定義した順番で値が代入されるので、定義した通りの順で引数指定をする必要があります。
この問題を解消するには、「名前付き引数」と言って、引数にキーを与えることで呼び出しやすくなる上、可読性も向上します。

使い方は、`function hoge({a, b, c}){}`と`({})`で定義をし、

```
// 通常の関数
function getUserData(name, age) {
  return `${name}さんは${age}歳です`;
}
console.log(getUserData("Kenta", 30));
console.log(getUserData(25, "Yuta")); //これでも処理は成功してしまう。

// 名前付き引数
function getProfile({ age = 20, name }) {
  return `${name}さんは${age}歳です`;
}

console.log(getProfile({ name: "たかし", age: 20 }));
```

## 課題

#### 【JS_7-1】 引数に金額を入れたら「税込〇〇円です」と出力する、taxInclude 関数を作成しましょう。

※不適切な引数だった場合のエラー処理も行ってください。

#### 【JS_7-2】 以下の要件を満たす関数を作成してください。

（要件）

- 関数名は getMessage とする。
- 関数実行時に渡される引数名を messageId とし、MSG00001~5 を受け取った際に対応するメッセージが出力されるようにしてください。
- 関数実行時に alert, confirm, console.log をのいずれかを渡し、messageId とは別に type という引数を受け取れるようにしてください。
- 引数の順番が入れ替わっても良いような対応をする。
  <br>

// メッセージリスト

```
const messageList = {
  MSG00001: "対象データがありません。",
  MSG00002: "処理が成功しました。",
  MSG00003: "保存してもよろしいですか？",
  MSG00004: "データを削除しました",
  MSG00005: "エラーが発生しました。\n管理者に問い合わせてください。",
};
```

---

# 8.アロー関数

## アロー関数

関数の記述方法としてアロー関数というものがあります。
復習として通常の関数の記述から説明します。

```
//一般的な関数の記述。
function hello(name) {
   console.log('hello' + name );
}

// hello taroと出力される。
hello(taro);

// constで変数宣言してから関数を記述する方法の場合は下記の記述になります。
const hello = function (name) {
   console.log('hello' + name );
}
```

この function の形を=>の記述に変更したものがアロー関数です。関数の記述を省略して簡潔に表すことができます。

```
// functionを=>の記述に変更する。
const hello = (name) => {
  console.log('hello' + name );
};

//引数nameのデフォルト値がない場合や引数が1つの時、{}の中身が一行の場合は省略ができます。
const hello = name => console.log('hello' + name );

//実用的な記述方法
const arry = [1, 2, 3, 4, 5, 6];

arry.forEach(function(value) {
  console.log(value);
});

//アロー関数で記述する。
arry.forEach(value => console.log(value));
```

## コールバック関数

引数に渡す関数のことをコールバック関数と呼びます。
JavaScript では関数を変数として扱うことが出来ます。

```
//hello関数の引数であるcallbackにgetName関数が格納されています。
function hello(callback) {
  //callback()にて文字列taroが戻り値として展開される。
  console.log("hello" + callback());
}

//こちらがコールバック関数です。戻り値として文字列taroを返します。
function getName() {
  return "taro";
}

//hello関数にコールバック関数であるgetNameが引数として記述されています。
//その結果、hello taroと出力されます。
hello(getName);
```

## 課題

#### 【JS_8-1】 以下の通常の関数を、arrow 関数で置き換えて提出してください。

※arrow にすることにより省略できる部分は極力省略してください。

```
function janken() {
  let number = rand(1, 3);
  let hand = "";
  switch (rand) {
    case 1:
      hand = "グー";
      break;
    case 2:
      hand = "チョキ";
      break;
    case 3:
      hand = "パー";
      break;
  }

  let message = "あなたは" + hand + "を出しました。";
  return message;
}
```

#### 【JS_8-2】 以下の通常の関数を、arrow 関数で置き換えて提出してください。

```
function getProfile({ name, age }) {
  return "私は" + name + "です。年齢は" + age + "歳です。";
}
```

---

# 9.this、bind

## this、bind

JavaScript での this とは、オブジェクトを参照するキーワードと定義されています。
this をどこで使用するか何を参照するかで中身が変化する変数です。

```
const human = {
   name: '山田',
   age: 20,
   printName: function() {
      //このthisではhumanオブジェクトのnameを呼び出しています。
      console.log(this.name);
   };
};
//山田が出力されます。
human.printName();
```

クラスの中で this を定義すると以下の記述になります。
クラスを記述した段階ではオブジェクトが生成される前なので、this を記述しプロパティに値を設定する必要があります。

```
class Person {
  //オブジェクトが生成される前なので、thisを記述しプロパティに値を設定します。
  constructor() {
    this.name = "山田";
    this.hobby = "サッカー";
  }

  introduction() {
    console.log("はじめまして、" + this.name + "です。");
  }
}
//オブジェクトを生成します。
const yamada = new Person();
//「はじめまして、山田です。」と出力されます。
yamada.introduction();
```

bind とは、関数に対して this や引数を指定することができるメソッドです。
関数内の this は関数自体を指す性質がありますが、その this を書き換えることによって参照するプロパティを変更できます。

```
function Person(name, hobby) {
  this.name = name;
  this.hobby = hobby;

  this.introduction = function () {
    console.log("名前:" + this.name + "　趣味：" + this.hobby);
  };
}

function Yamada(name, hobby) {
  this.name = name;
  this.hobby = hobby;
}

// nameに田中、hobbyにサッカーが格納されます。
let person = new Person("田中", "サッカー");

// nameに山田、hobbyにバスケが格納されます。
let yamada = new Yamada("山田", "バスケ");

//bindでプロパティの参照元を変更できます。
//　名前:山田　趣味：バスケ　と出力されます。
person.introduction.bind(yamada)();
```

## 課題

#### 【JS_9-1】 名前(name)、タイプ(type)、レベル(level)を定義したコンストラクタを作成し、例のような出力をさせてください。

（例）ピカチュウは電気タイプでレベル５２です。

#### 【JS_9-2】 以下のコードを編集して、最終的に「こんにちは。私はハルクです。年齢は 40 歳で趣味は裁縫です。」と出力させてください。

```
function Person(name, age) {
  this.name = name;
  this.age = age;

  this.self_introduction = function () {
    console.log(
      "こんにちは、" + this.name + "です。年齢は、" + this.age + "歳です。"
    );
  };
}

function Dog(name, age) {
  this.name = name;
  this.age = age;
}

var taro = new Person("太郎", 23); // 太郎という人間
var hachi = new Dog("ハチ", 5); // ハチというイヌ

taro.self_introduction.bind(hachi)();
```

---

# 10.クラス

## クラス(class)

クラス(class)は、オブジェクトが所持する変数やメソッドなどを定義した、ある程度の機能のまとまりと定義します。クラスからオブジェクトの実体を生成することで変数やメソッドを実行できます。

クラスの記述方法は以下の記述になります。

```
class クラス名 {
  変数や処理を記述する;
}
```

クラスには constructor というオブジェクトを生成する際に、初期化関数として呼ばれるメソッドを定義するものがあります。

```
//FullNameというクラスを宣言します。
class FullName {
  //constructorでクラスを生成した際にクラスの初期設定を行う。
  constructor(firstName, lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }
}

//インスタンスを生成するにはnew クラス名を記述します。
let human = new FullName("太郎", "山田");
```

クラスの中にメソッドを定義することもできます。
メソッドを呼び出す記述は以下の通りです。

```
class Human {
  constructor(name, age, job, hobby) {
    this.name = name;
    this.age = age;
    this.job = job;
    this.hobby = hobby;
  }

  //メソッドをクラスの中に定義する。
  getName() {
    return this.name;
  }
}

//Humanクラスからインスタンスを生成。
let yamada = new Human("山田", "26", "エンジニア", "サッカー");

//getNameメソッドが呼び出され、山田が出力される。
console.log(yamada.getName());
```

クラスを継承することもできます。ある親クラスの内容を引き継いだ子クラスを作成することを継承するといいます。クラスの継承を行うには`extends`キーワードを使用し、継承した子クラスからは親クラスの所有するメソッドやプロパティを使用することができます。

```
//親クラスを継承する記述方法。
class クラス名 extends 親クラス名 {
  // クラスの定義
}

//Dogクラスを定義します。
class Dog {
  dogName() {
    return "シバ犬";
  }
}

//CatクラスにDogクラスを継承します。
class Cat extends Dog {
  catName() {
    return "スコティッシュ・フォールド";
  }
}

//Catクラスのインスタンスを生成します。
let animal = new Cat();
console.log(animal.dogName()); //シバ犬が出力されます。
console.log(animal.catName()); //スコティッシュ・フォールドが出力されます。
```

## 課題

#### 【JS_10-1】 Animal という動物を管理するクラスを作成し、name,type,age をコンストラクタとして設定してください。

#### 【JS_10-2】 Animal クラスを用いて cat というインスタンスを生成し、1 件データを出力してください。

#### 【JS_10-3】 問題１の Animal クラスを継承した Cat クラスを作成し、新たに tall（身長）もコンストラクタに追加してください。

#### 【JS_10-4】 Cat クラスを用いて 1 件インスタンスを生成し、出力してください。

---

# 11.DOM 操作での CRUD 処理

## DOM

DOM(Document Object Model)とは、HTML を JavaScript で操作するための仕組みのことです。
DOM ツリーという階層構造になっており情報を格納されています。
HTML の情報の取得や変更、イベントの登録ができます。
DOM 操作を行うには、ブラウザに格納されている document の情報を使用して記述を行います。

※CRUD・・・CRUD とはデータの作成(Create)、読み出し(Read)、更新(Update)、削除(Delete)を表す言葉のことです。

```
<html>
  <head>
    <meta charset="utf-8" />
    <link rel="stylesheet" href="app.css">
  </head>
  <body>
    <div id="box1"></div>
    <script src="main.js"></script>
  </body>
</html>
```

```
//documentからbox1の情報を取得し、box1に格納します。
const box1 = document.getElementById('box1');

//box1のstyleの情報を変更します。
box1.style.color = 'red';

//classListプロパティからaddメソッドを呼び出し、クラス名を追加します。
//クラス名にmainBoxが付与されます。
box1.classList.add('mainBox');
```

こちらを参考にしてください ↓

https://zenn.dev/ryofrontenginer/articles/edfce254795efc
https://www.fenet.jp/dotnet/column/language/6526/

![](https://www.autumn-group.com/wp-content/uploads/2023/10/989aad314925-20220309.png)

## 課題

#### 【JS_11-1】 以下の要件に従った処理を実装しましょう。

簡易的なフォームとリストを用意しました。

- 「処理開始」ボタン押下時に、カードのチェックボックスの値に従いそれぞれ処理を行う
- 「複製」にチェックがあれば、チェックしたカード要素を複製し、一番下に追加する
- 「変更」にチェックがあれば、カードナンバーの数字を 0 ~ 1000 のランダム値で入れ替える
- 「削除」にチェックがあれば、カード要素を丸ごと削除する
- チェックボックスは１つしか入力できないように制御を入れる。
  ※ 以上が実装できれば、クラス名や各プロパティ値は自由に修正して構いません。

# 12.JS アニメーション

さて、JavaScript の文法を中心に進めてきましたが、やはり JavaScript といえばアニメーションのイメージもあるでしょう。今回は、JavaScript のフレームワークである jQuery を用いて簡易的にアニメーションの実装をしてみましょう！

#### 【JS_12-1】 以下のモーダル画面を実装してください。

※Close ボタンもしくはモーダルの外側をクリックした際に、モーダルが閉じるようにしてください

![](https://www.autumn-group.com/wp-content/uploads/2023/10/a66085224f24-20220310.gif)
:::details html ファイル

```
<!DOCTYPE html>
<html lang="ja">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta name="robots" content="noindex" />
	<link rel="stylesheet" href="style.css">
	<title>モーダル</title>
</head>

<body>
	<div id="overlay" class="overlay"></div>

	<!-- モーダルウィンドウ -->
	<div class="modal-window">
		<p>モーダルウィンドウです。</p>
		<!-- 閉じるボタン -->
		<button class="js-close button-close">Close</button>
	</div>

	<h2 class="section-title">モーダル</h2>
	<!-- 開くボタン -->
	<button class="js-open button-open">open</button>

	<script src="https://code.jquery.com/jquery-3.5.1.js"
		integrity="sha256-QWo7LDvxbWT2tbbQ97B53yJnYU3WhH/C8ycbRAkjPDc=" crossorigin="anonymous"></script>
	<script type="text/javascript" src="main.js"></script>
</body>

</html>
```

```
* {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
	list-style: none;
  }

  button {
	cursor: pointer;
	-webkit-appearance: none;
	-moz-appearance: none;
	appearance: none;
	vertical-align: middle;
	color: inherit;
	font: inherit;
	border: 0;
	background: transparent;
	padding: 0;
	margin: 0;
	outline: none;
	border-radius: 0;
  }

  .overlay {
	display: none;
	position: fixed;
	top: 0;
	left: 0;
	background-color: rgba(0, 0, 0, 0.5);
	width: 100%;
	height: 100%;
	z-index: 10;
  }

  .modal-window {
	display: none;
	position: fixed;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	width: 300px;
	height: 300px;
	background-color: #dfdddd;
	border-radius: 5px;
	z-index: 11;
	padding: 2rem;
  }

  .button-close {
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	width: 200px;
	padding: 1em;
	background-color: #c96931;
	color: #eaeaea;
	border-radius: 20rem;
	cursor: pointer;
  }


  .section-title {
	text-align: center;
	margin: 2em;
	font-size: 20px;
  }

  .button-open {
	display: block;
	margin: 0 auto;
	width: 20rem;
	padding: 1em;
	background-color: #3140c9;
	color: #eaeaea;
	border-radius: 20rem;
	cursor: pointer;
  }
```

#### 【JS_12-2】 以下のサイズ変換機能を実装してください。

![](https://www.autumn-group.com/wp-content/uploads/2023/10/2d286e27e2d0-20220310.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>サイズ変換</title>
	<link rel="stylesheet" type="text/css" href="style.css">
	<!-- jQuery -->
	<script src="https://code.jquery.com/jquery-3.6.0.min.js"
		integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
	<script type="text/javascript" src="main.js"></script>
</head>

<body>
	<p>横幅</p>
	<input type="range" id="width" min="1" max="300">
	<p>縦幅</p>
	<input type="range" id="height" min="1" max="300">
	<div class="box"></div>
</body>

</html>
```

```
.box{
	background-color: salmon;
	width: 100px;
	height: 100px;
  }
```

#### 【JS_12-3】 以下のハンバーガーメニューを実装してください。

![](https://www.autumn-group.com/wp-content/uploads/2023/10/9aaa919e7359-20220310.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>ハンバーガーメニュー</title>
	<link rel="stylesheet" type="text/css" href="style.css">
	<!-- jQuery -->
	<script src="https://code.jquery.com/jquery-3.6.0.min.js"
		integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
	<script type="text/javascript" src="main.js"></script>
</head>

<body>
	<div class="icon" id="open">
		<span class="top bar"></span>
		<span class="middle bar"></span>
		<span class="bottom bar"></span>
	</div>
	<nav class="menus">
		<ul class="menu-list">
			<li><a href="#">ホーム</a></li>
			<li><a href="#">コンタクト</a></li>
			<li><a href="#">アクセス</a></li>
			<li><a href="#">ニュース</a></li>
		</ul>
	</nav>
</body>

</html>
```

```
body{
	margin: 0;
	padding: 0;
  }
  .icon{
	position: relative;
	width: 30px;
	height: 30px;
	background-color: mediumblue;
	padding: 10px;
	cursor: pointer;
	z-index: 2;
  }
  .bar{
	position: absolute;
	width: inherit;
	height: 3px;
	background-color: white;
	border-radius: 5px;
  }
  .top{
	top: 28%;
  }
  .middle{
	top: 48%;
  }
  .bottom{
	top: 68%;
  }
  #close .top{
	transform: rotate(45deg);
  }
  #close .bottom{
	transform:rotate(-45deg);
  }
  .menus{
	background-color: mediumblue;
	width: 300px;
	position: fixed;
	top: 0;
  }
  .menu-list{
	list-style: none;
  }
  .menu-list a{
	text-decoration: none;
	color: #fff;
	display: block;
  }
  .menu-list li{
	line-height: 2em;
  }
```

# 13.CSS アニメーション

JavaScrip でアニメーションをしていただきましたが、実は簡易的なアニメーションは CSS で実装することが多いです。まずは CSS アニメーションの基本を学習し、課題に取り組んでみましょう。

### 1.アニメーションの定義名(animation-name)

（例）animation-name: fadeInAnime;
アニメーションの定義名は半角英数字で自由に決めることが可能。
animation-name につけた定義名に対し、keyframes でアニメーションの開始から終了までの変化を指定。

```
@keyframes fadeInAnime {
  0% {
    /*ここに開始のCSSを記述*/
  }

  100% {
    /*ここに終了のCSSを記述*/
  }
}
※0%
  ~ 100%の間には20%、60%といった間の動きの設定の追加も可能。
  ※0%
  ~ 100%はfrom
  と
  to
  でも代用できます。
  @keyframes
  fadeInAnime {
  from {
    /*ここに開始のCSSを記述*/
  }

  to {
    /*ここに終了のCSSを記述*/
  }
}
```

### 2. アニメーションの開始と終了時の状態を指定（animation-fill-mode）

（例）animation-fill-mode:backwards;
none→ 指定なし。初期値。
forwards→ 元の状態に戻らずアニメーション最後の状態を維持
backwards→ アニメーションの最初の状態に戻る
both→backwards と forwards の両方の状態を適用

### 3. アニメーション１回分の時間の長さを指定（animation-duration）

（例）animation-duration:3s;
1.5 秒なら →1.5s（初期値は 0）

### 4. 動きをループさせる（animation-iteration-count）

（例）animation-iteration-count:infinite;
infinite→ 無限に再生を繰り返す
数値 → 数値で再生回数を指定する（初期値は 1）

### 5. アニメーションの進行具合を操作（animation-timing-function）

（例）animation-timing-function:ease;
ease→ 初期値：開始時と終了時が緩やかに変化
ease-in→ 開始時は緩やかに変化、終了に近づくと早く変化
ease-out→ 開始時は早く変化し、終了時は緩やかに変化
ease-in-out→ 開始時と終了時は、かなり緩やかに変化
linear→ 開始から終了まで一定に変化
steps(数値, start または end)→ パラパラ漫画のように数値をコマ数で変化
cubic-bezier（数値をカンマ区切りで 4 つ指定）→ 変化の進行割合を 3 次ベジェ曲線で指定

### 6. アニメーションの開始を遅らせる（animation-delay）

（例）animation-delay: 0.5s;
3 秒なら →3s（初期値は 0）

### 7. アニメーション再生の向きを順方向、逆方向、前後反転のいずれにするかを決める（animation-direction）

（例）animation-direction:normal;
normal→ 初期値：普通方向の再生で動きを繰り返す
reverse→ 逆方向の再生で動きを繰り返す
alternate→ 奇数回では普通方向、偶数回では逆方向の再生で動きを繰り返す
alternate-reverse→ 毎回逆方向の再生、奇数回では逆方向、偶数回では普通方向

## 課題

#### 【CSS_13-1】 以下のテキストボタンを実装してください。

![](https://www.autumn-group.com/wp-content/uploads/2023/10/f24c74ff4800-20220310.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css"
		href="http://coco-factory.jp/ugokuweb/wp-content/themes/ugokuweb/data/move02/5-1/css/reset.css">
	<link rel="stylesheet" type="text/css" href="style.css">
	<title>テキストボタン</title>
</head>

<body>
	<div class="btn">テキストボタン</div>
</body>

</html>
```

#### 【CSS_13-2】 以下のツールチップを実装してください。

![](https://www.autumn-group.com/wp-content/uploads/2023/10/3a51077e49b2-20220310.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css" href="style.css">
	<title>ツールチップ</title>
</head>

<body>
	<div class="box">
		<div class="image">画像 or テキスト</div>
		<div class="text">ここに説明などを入れます</div>
	</div>
</body>

</html>
```

#### 【CSS_13-3】 以下のアニメーションを実装してください。

※一定時間で色が変化していくアニメーションです。
![](https://www.autumn-group.com/wp-content/uploads/2023/10/993798acb3d7-20220310.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css"
		href="http://coco-factory.jp/ugokuweb/wp-content/themes/ugokuweb/data/move02/5-1/css/reset.css">
	<link rel="stylesheet" type="text/css" href="style.css">
	<title>背景変化</title>
</head>

<body>
	<p>背景色が時間とともに変化</p>
</body>

</html>
```

#### 【CSS_13-4】 以下の SNS アイコンを実装してください。

![](https://www.autumn-group.com/wp-content/uploads/2023/10/daedd5d53c20-20220310-1.gif)

```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<link rel="stylesheet" type="text/css"
		href="http://coco-factory.jp/ugokuweb/wp-content/themes/ugokuweb/data/move02/5-1/css/reset.css">
	<link rel="stylesheet" type="text/css" href="style.css">
	<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.6.3/css/all.css"
		integrity="sha384-UHRtZLI+pbxtHCWp1t77Bi1L4ZtiqrqD80Kn4Z8NTSRyMA2Fd33n5dQ8lWUE00s/" crossorigin="anonymous">
	<title>SNSアイコン</title>
</head>

<body>
	<div class="container">
		<ul>
			<li>
				<a href="#"><i class="fab fa-facebook-f icon"></i> </a>
			</li>
			<li>
				<a href="#"><i class="fab fa-twitter icon"></i></a>
			</li>
			<li>
				<a href="#"><i class="fab fa-linkedin-in icon"></i></a>
			</li>
			<li>
				<a href="#"><i class="fab fa-google-plus-g icon"></i></a>
			</li>
		</ul>
	</div>
</body>

</html>
```

以上で JavaScript(CSS アニメーション含む)のセクションは終了です！
お疲れ様でした！
