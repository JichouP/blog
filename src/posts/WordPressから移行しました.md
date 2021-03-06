---
title: 'WordPressから移行しました'
date: '2019-01-08'
---

お久しぶりです．JichouP です．
かなり時間がかかりましたが（2 ヶ月くらい？）自前で静的サイトジェネレーターを作ったので紹介します．（GitHub に転がってるので使いたかったらご自由にどうぞ．ライセンスは MIT です．）

## 使ってる（主な）技術

- ロジック
    - TypeScript
        - JS に型がつくよ！やったね
    - React
        - 言わずもがな
    - Parcel
        - フォルダ内のファイルをワイルドカードでまとめて Import できる（Webpack だと`require.context`とかいう黒魔術っぽいものを使う必要があるので Parcel を採用）
    - StyledComponent
        - ReactComponent にスタイルがくっつけられるやつ．
- デザイン
    - Vivus
        - ロゴのアニメーション
    - Snap
        - ロゴのアニメーション
    - google-code-prettify
        - コードブロックのスタイリング

## 強いところ

- `Contents` フォルダに Markdown で書かれた記事を追加するだけで記事が生える．
    - これは Parcel のおかで検索してもなかなか記事や Issue が出てこないのでいつか記事にしたい．
- こんなふうに，コードブロックがいい感じになる
    - `google-code-prettify`のおかげ．スタイルがいろいろあって便利．

```ts
const add = (a: number, b: number): number => a + b;
console.log(add(4, 5)); // 9
```

- ロゴかっこよくない？
    - 一晩で作った．SVG 触ったことなかったけどこのくらいなら結構簡単．
- Markdown の中で画像を使用してもちゃんと Parcel が生成した画像にパースできる（ここだけ自前実装）
    - 記事を書くときにも画像リンクの補完が効くし，プレビューにもちゃんと出る．

## 辛かったこと

Parcel のワイルドカードインポートの仕様がわかるまでに時間がかかった．
CSS がなかなか思うようにならなかった．

## 気になる点

- 静的サイトなので閲覧数カウンタとか記事コメントとかがつけられない．
    - 気になる点があったら Twitter でリプください．
- **ダサい．**
    - シンプルイズベストってことで．ブログだし．ポータルサイトの方はもっといい感じにしたい．
- ロゴマークがトップページへのリンクであることに気付けない．
    - ユーザーがクリック可能オブジェクトだと認識するためにはどうしてもクリック可能領域を見せる必要があるけど，ロゴを四角で囲みたくなかった故こうなってしまった．アニメーションでごまかしてるけど，他になんかいい方法あったら教えてください．
- 画像の圧縮とか全く考えてない．
    - WordPress だと自動でいろいろなサイズを生成してますよね．でもあれは動的サイトなので，僕のシステムで実装するにはいい感じのツールを書かなきゃいけないですね．というか，レスポンスが良くなるだけで通信量は増えるので却下です．
- タグが付けられない．
    - さっさと実装しろ．

## 感想

GatsbyJS を使おうか迷ったんですけど，あそこまでの機能は要らないというのと，ロジックも全部自分で作ることによる全能感を味わいたかったので使いませんでした．書いていてとても楽しかったです．
シンプルですが，`react-router`を使った公開サイトはこれが初めてなのでいろいろ勉強になりました．
少しだけ Hack が溜まったのでいつか書きたいですね．
