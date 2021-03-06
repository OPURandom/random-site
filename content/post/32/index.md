---
title: 'Rectas'
# [必須]タイトル 短めで！
subtitle: 'made by Flutter' # 記事のタイトルの下に表示
summary: 'Made by Flutter' # Cardに表示 無かったら本文1行目が入る 短めで！
math: true # Tex いらないならfalse
diagram: false # グラフ描画 必要ならtrue
authors:
- pngn
# [必須] 著者 一応複数人かけるけどアイコン表示は一番上の人だけ
tags:
- '活動紹介'
# [必須] タグ 複数可 既にあるタグを使おう
 # 作品紹介系テンプレ: 作品紹介, ゲーム, 音楽, グラフィック
 # ブログ系テンプレ: 競技プログラミング, ゲーム制作, DTM, LT会
date: "2020-01-03T00:00:00Z"
# [必須]
lastmod: "2020-01-03T00:00:00Z"
# [必須] 今日の日付を入れよう(これを元に最新記事取ってきてるはず)
featured: false # ???
draft: false # true にすると非表示になる
top_show: true

# [必須] 同一フォルダにfeatured.jpg/pngを入れて! 絶対!

projects: [] # project関係あればその名前を入れる

# 本文の書き方はこれを参照して(https://sourcethemes.com/academic/docs/writing-markdown-latex/)
---
# はじめに
こんにちは。情報2回のpngnです。皆さんはHugoってご存知ですか？僕はこのサイトを作り始めるまで知りませんでした。よく知らない方のためにかいつまんで特徴を説明すると

- 静的サイトジェネレーター(つまりphpとかサーバー側で動かす処理が書けない)  
- Goで書かれていて速い  
- マークダウンで書ける
- 静的サイトなのでGithub PageやNetlifyが無料で使える  

らしいです。今回はAcademicというHugoのテーマを利用しました。
  
この記事はこのサイトを使いたい方(つまり部員)とAcademicのテーマをソースレベルでいじりたい方(いるのかなぁ)に向けて書かれています。  
  
# Hugoの使い方
自分のパソコンでHugoを動かしたい人はやりましょう。Academicを使うためにHugo Extendedを[このページ](https://github.com/gohugoio/hugo/releases)からダウンロードしてインストールします。**Extended**をダウンロードする事に注意。このサイトのテーマのソースコードは[ここ]()からダウンロードできます。  
gitでcloneしてきて、そのrootフォルダに移動してターミナルで

```bash
 > hugo server  
```

と打ちましょう。http://localhost:1313/でアクセスできるようになります。ビルドはhugoコマンドです。  
  
コンテンツは基本的にcontentフォルダに入っています。その中でAcademicにおいて特別に意味のあるフォルダを紹介します。

- authors: 著者 ([テンプレート](./data/authors.zip))
- post: ブログ ([テンプレート](./data/post.zip))
- slides: スライド ([テンプレート](./data/slides.zip))
- project: プロジェクト
- home: トップページ

基本的にそれぞれのフォルダの中に記事のフォルダを入れて、その中にindex.md(authorsは\_index.md)とfeatured.png/jpgを入れるとOKです。画像は縦横比3:4のものが理想です。index.mdはテンプレートを参考に書いて下さい。カスタムCSSも使えます。  

# Academicのカスタマイズ
これ需要あるのか分からないですが、僕がAcademicをいじった時つまった事を共有しておきます。

- /themes/academic/の中のどのファイルをいじればいいか分からない  
  - だいたい/layouts/partials/の中  
  - たまに/layouts/\_default/とか/layouts/section/とか  
  - CSSは/assets/scss/の中  
  - どうしても分からない時はacademicのgithub内検索  
  - ファイルの中身を一時的に消してどう変化するかを見ると分かりやすいよ
- ライブラリのコードをいじる際、たまにHot Reloadがかからない事がある
  - hugo serverし直せばよい
- Hugo独特の書き方がキモい(はい)
- AcademicはTagに日本語が入るとリンクが切れるバグ？があるので注意
  - /layouts/partials/tags.htmlをいじるとなおった  

いかがでしたか？何の役にも立ちませんね。そもそもテーマのソースをいじろうと思う人って僕のアドバイスなんて必要ないですよね。おわり  

# 思った事
ここまで読んで、pngnってWebつよつよマンなんだなぁって思われるかもしれないですが、実は僕Web初心者です。html触るの久しぶりだしCSSはノリで書いてるのでゴミコードを書いてしまった気がします。そんな僕が今回Webを作って思った事を書きます。  
そもそもhtmlってトップダウンでできてますよね。簡単に言うと親から順番にDOMが決まるって事です。子要素が親DOMの情報に依存する...けれども親の情報を取るのは簡単じゃない状況ってモジュール化の観点で微妙な気がします。例えば親にかかっているCSSによって子要素のデザインは変化しますが、それが何か知ることは出来ないですよね？(あったら教えて下さい)それが大規模開発における複雑さの原因になりうると僕は思います。後は同じソースにhtml, js, css, hugoやphpなど複数の言語が存在するのは複雑だし、CSSでPCとスマホ両方に対応させないといけないの大変ですよね。クロスプラットのflutter、Web版はCanvasで描かれているようで、現状遅いです。今後に期待  

# まとめ
部員のみんなは記事書いてね
