# 正規表現10本ノック（導入編）

対象者：
  * 「正規表現」について何も知らないけど、なんとなく知ってたら便利そうと思ってる人

目的：
  * 正規表現に触れる
  * どういったものかを理解する(食わず嫌いや、無知による恐れを克服する)
  * テキストエディターの検索などで簡単な正規表現の検索ができるようになる(活用できる)

# 出題形式：

各出題は以下の構成を取る

## 出題：正規表現0本目

```
以下の文字列のうち○の行にマッチするが、×の行にマッチしない正規表現を書いてください

    ○: regexp
    ×: hogehoge

  正規表現： _____ （<-- ここに入力といった感じのサイトを作りたい）
  文字数の目安: 6文字 (正解となる正規表現文字列の文字数の目安。出題者が素直に考えた正規表現はこの文字数になるので、正解を考える目安としていただきたい)
  上級者向け: 12文字  (出題者がわざと素直じゃない書き方で考えた正規表現の文字数。わかる方はこの文字数での回答に挑戦してみて欲しい)
```

## 回答方法:

検討中

## 解説：正規表現0本目

問題のポイントと用語の解説を行う

正規表現は「普通の文字」と「特殊な文字」を組み合わせて記述します。ここでは「普通の文字」をただ書くだけの出題となっています。
これも立派な正規表現です。

なお、上級者向けの制限に対する回答では「特殊な文字」を駆使して自由に正規表現を書く力を振るってください。

<!--
* 「regexp」とは：正規表現は英語で"Regular Expression"と言い、略してregexp, regex, regx, re などと書く時がある
* 「hogehoge」とは：その文字列に特段意味のないことを表す文字列、バリエーションに「fugafuga」「piyopiyo」などがある。([メタ構文変数](https://ja.wikipedia.org/wiki/%E3%83%A1%E3%82%BF%E6%A7%8B%E6%96%87%E5%A4%89%E6%95%B0#:~:text=%E6%97%A5%E6%9C%AC%E3%81%AE%E3%81%BF%E3%81%A7%E4%BD%BF%E7%94%A8%E3%81%95%E3%82%8C,%E3%81%BB%E3%81%92%EF%BC%89%E3%80%8D%E3%81%AA%E3%81%A9%E3%81%8C%E3%81%82%E3%82%8B%E3%80%82))
* 「マッチ」とは正規表現と文字列を照合すること、正規表現により目的の文字列が検索できたら「マッチした」という
-->

# 出題の全体像

10本程度の出題をこなす事で目的を果たすようになることを目指す

* [正規表現10本ノック0本目](knock000.md): シンプルな検索 (連結)
* [正規表現10本ノック1本目](knock001.md): 複数種類の文字列にマッチする正規表現(選択、特殊な文字(メタ文字) "|")
* [正規表現10本ノック2本目](knock002.md): 特殊な意味を消す特殊な文字（エスケープ文字 "\"）
* [正規表現10本ノック3本目](knock003.md): 特殊な意味を与える特殊な文字（エスケープ文字と英数字 "\t", メタ文字 "\s"）
* [正規表現10本ノック4本目](knock004.md): あらゆる文字にマッチする正規表現（メタ文字 "."）
* [正規表現10本ノック5本目](knock005.md): 繰り返しを表す正規表現(メタ文字 "*", "+")
* [正規表現10本ノック6本目](knock006.md): グルーピング(正規表現の組み合わせ) (メタ文字 "(…)")
* [正規表現10本ノック7本目](knock007.md): 繰り返しを表す正規表現(メタ文字 "?")
* [正規表現10本ノック8本目](knock008.md): 文字クラス(メタ文字 "[…]")
* [正規表現10本ノック9本目](knock009.md): 場所にマッチする正規表現(メタ文字 ^, $)

# メタ文字の一覧

参考: https://github.com/k-takata/Onigmo/blob/master/doc/RE.ja

# 正規表現で表せるもの

ノックが終わった後は、以下の正規表現が読めるか確認してみてください。

* 数字: [0-9]+,  [0-9]\(.[0-9]+)?
* 一般的なプログラム言語の変数名: [a-zA-Z_][a-zA-Z_0-9]* (多くのプログラミング言語で変数名には_も含むこと、数字で始まらないことに注意)
* ダブルクォートで囲まれた文字列: ".*"  (このような表現を実用的に使おうとすると「貪欲マッチ」や「最短マッチ」について知る必要が出てきます)
* ダブルクォートで囲まれたPython文字列: "(\\\\.|[^\\\\"]+)*"  (これは上級者用です。これが読めなくても問題ないですが、この正規表現を使うと "abc\"def" というダブルクォート文字列もマッチできます。)

# 2週目、中級者向けに扱うもの

1. 繰り返し {m,n}
1. 文字コード(ASCII、Unicode)で指定するメタ文字(\xHH, \uHHHH)

# コラム

そのうち書くかも（まだ中身はない)

* コラム：正規表現のオプションgについて
* 正規表現でのアルファベットの大小区別(正規表現のオプションi)
* 正規表現での改行の扱いその1 (正規表現のオプションm 複数行モード (\A, \Z, \z))
* 正規表現での改行の扱いその2 (正規表現のオプションs 単一行モード ("."))
* 正規表現で表せないもの。「括弧のネスト」など
* 正規表現の拡張 (?…)
* プログラミング言語からの利用(検索、判定、置換、抽出)
* プログラミング言語からの利用(メタ文字\Gが必要な時はどんな時？)
* 8進数でのコード指定と落とし穴
* 正規表現内のエスケープ文字とプログラミング言語自身のエスケープ文字の解釈

# この導入編で扱っていないもの

1. キャプチャと後方参照
1. 名前付きキャプチャと後方参照
1. 先読み（lookahead)、後読み(lookbehind)、正規表現の先と後って？
1. 最短マッチ (最小量指定子(reluctant quantifier))、貪欲マッチ (最大量指定(greedy quantifier)、バックトラック
1. 強欲マッチ (絶対最大量指定子(possessive quantifier))
1. モード修飾 (?imx-imx), (?imx-imx:…)
1. アトミックグループ(atomic grouping)
1. オプションx (extended)
1. コメント (?#…)
1. ループ展開
1. パフォーマンス
1. NFAとDFA
1. POSIX 文字クラス
2. 部分式呼び出し(subexpression call)
3. 条件分岐
4. 非包含オペレーター (absence operator)
5. Javaの文字クラスの集合演算
