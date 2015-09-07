# CoffeeScript Coding Style Guide

- [はじめに](#はじめに)
- [インデント / 空白 / セミコロン](#インデント--空白--セミコロン)
- [文字数](#文字数)
- [文字列 / 配列 / ハッシュ](#文字列--配列--ハッシュ)
- [演算子](#演算子)
- [変数名](#変数名)
- [関数](#関数)
- [その他推奨・非推奨事項](#その他推奨非推奨事項)
- [関連資料](#関連資料)

## はじめに
  - 細かいスタイルについてはCoffeeLintの設定ファイル（coffeelint.json）に従う
  - 実装上不都合が出てきた場合、適宜判断し改修を行う（issueをお願いします）
  - 詳細については[Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)([日本語](http://cou929.nu/data/google_javascript_style_guide/))を参考にする
  - これらのガイドを参考にしています
    - [Cookpad | Cookpad CoffeeScript Coding Style Guide](https://github.com/cookpad/styleguide/blob/master/coffeescript.ja.md)
    - [GitHub | Coding Style](https://github.com/styleguide/javascript)

## インデント / 空白 / セミコロン
  - 2スペースとする
  - 行末の空行は禁止
  - 演算子の前後には空白を1つずつ空ける
  - ,の後には1つ空白を空ける
  - セミコロンは必然性がない限り省略する

## 文字数
  - 可能な限り120文字以内とする。エラーメッセージ文言などはその限りではない

## 文字列 / 配列 / ハッシュ
  - 基本的にシングルクォートを使用する
  - 式展開を行う場合、```"#{foo}"```を使用すること
  - +演算子を用いた式展開は使用しない
  - 複数行の文字列には```"""..."""```を使用できるがHTMLは可能なかがりHTMLとして記述すること。レスポンスが複雑かつ更新を伴うものの場合この限りではない
  - 複数行の配列、ハッシュを記述する場合には,を省略する
  - ハッシュを一行で記述する場合、{}の前後に1つ空白を空ける ```{ foo: bar }```  
  ※ ハッシュだけであることに注意すること。ハッシュ以外の場合、空白は入れない```"Hello World, ${name}!"```

## 演算子
  - 以下の演算子を使用すること  
  ```&&, ||, ==, !=```
  - [WIP]コードの統一のため以下のエイリアスは使用しないこと  
  ```and, or, is, isnt```

## 変数名
  - 変数名はcamelCaseを用いる
  - クラス名はPascalCaseを用いる
  - 定数は全て大文字でSNAKE_CASEを用いる
  - 一般的でない特定しにくい省略は避けること
  - [WIP] jQueryの使用に限らずDOMは$開始とすること
  - 文言等の文章は可能な限り一箇所にまとめ、定数として定義すること  
  ```
  text =
    SUCCESS_AJAX: '通信に成功しました'
    ERROR: 'エラーが発生しました'
  ```

## 関数
  - ```->```の前後にはスペースを空けること
  - 引数がない場合、括弧は省略すること
  - メソッド呼び出しの括弧は省略しないこと
  - メソッドとメソッドの間には改行をいれること
  - thisの保持には```=>```を使用すること
  - 必然性のないfat allow```=>```は使用しないこと
  - [WIP]イベントが引数として使用される場合、eやevtと省略せずeventとすること```(event) -> some.action()```
  - [WIP]thisの保持が必要な場合、```_this = this```とすること
  - [WIP]単体のthisは避けること。単体でない場合、積極的に使用すること  
  ```
  $(this) # OK
  $(@) #NG
  $(this.foo) #NG
  $(@foo) #OK
  ```

## その他推奨・非推奨事項
- JavaScript埋め込みは使用しないこと
- JavaScript / CoffeeScriptからDOMにアクセスする場合、そのDOMのクラスにjs-プレフィックスを付与すること[Stylesheet Style Guide参照]
- JavaScript / CoffeeScriptからスタイルの更新を行う場合、スタイルのプロパティを変更するのではなくクラスの付け替えで行うこと。ドラッグ、タッチはこの限りではない
- JavaScript / CoffeeScriptからスタイルの更新を行う場合のクラス名はis-プレフィックスを使用すること[Stylesheet Style Guide参照]

## 関連資料
- [Hands on Front-end :-) with CoffeeScript](https://github.com/khirayama/handson-front-end)
