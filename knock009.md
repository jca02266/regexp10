# 出題：正規表現10本ノック9本目(メタ文字 `^`, `$`)

## 背景

あなたはプログラマです。もうこのプログラムを消してしまいたくなりました。

```vb
  Dim foo as Long
  Dim bar as Long
  Dim baz as Long
```

## お題
以下の文字列のうち、○の文字列にマッチして×の文字列にマッチしない正規表現を考えてください。
（冒頭の背景のことは無視してください。置換のことは考えなくて良いです)

    ○: Dim foo as Long
    ○: Dim bar as Long
    ○: Dim baz as Long
    ×: Dim foo as Long: foo = 123
    ×: ' Dim foo as Long

使用する正規表現の条件:
  * 文字数の目安: 6〜11文字(メタ文字 `^`, `$`、`.`, `*`を使用)   <!-- ^D.*g$ や ^Dim.*Long$ -->

## 解説

→[解説・回答はこちら](knock009_ans.md)
