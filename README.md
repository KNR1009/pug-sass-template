# pug-sass-template

- pug-sass 用のプロジェクトテンプレート

## 開発環境

yarn で gulp を走らせて src ディレクトリのソースを dist に出力します。
yarn は最新の version にしてください。

```
$ cd src
$ yarn (初回のみ)
$ yarn gulp もしくは yarn dev（実行するとdistディレクトリに出力されます。）
```

ローカル環境が自動で立ち上がります

## 使用技術

- pug([pug の書き方](https://qiita.com/takeshisakuma/items/fdcf456d8250e6dafc7b))

HTML を効率的に書くためのテンプレートエンジン

- sass([sass の書き方](https://qiita.com/nchhujimiyama/items/8a6aad5abead39d1352a))

CSS を拡張したもの

- jQuery

## CSS 設計について

- クラス名は BEM を採用
- CSS 設計は「[FLOCSS](https://qiita.com/super-mana-chan/items/644c6827be954c8db2c0)」でコーディングをしています

## ディレクトリ構成

### pug/dxx

HTML(pug)を記述していくディレクトリになっています。
最終的に index.pug にコンポーネントやレイアウトファイルを読み込ませます

### pug/dxx/Object

この中に component(ボタンなどの小さい単位)たプロジェクト(セクションごとの単位)を格納して、最終的に index.pug にて読み込んでいます。
ファイル名に関しては、コンポーネントの場合は「c-xx」で、プロジェクトの場合は「p-xx」と命名してください。

### sass/dxx/

FLOCSS 設計で構成されています。

/fundation は共通ファイルなので基本いじらない(h1,h2 などのリセット css など)
/object は pug で命名したものと同じ。ここにコンポーネントやプロジェクトのスタイルを当てていきます

書くファイルごとに\_index.scss というエントリーポイントがあるので、こちらに読み込みを行ってください。
最終的には/sass/style.scss に全てのディレクトリのエントリーポイントファイルを読み込んでいきます

### js/script.js

jQuery ファイルを読み込んでいます。(あんまりない)

### images/dxx

画像は全てこちらに格納してください。

## 納品形式

納品は html ファイルとして提出するので出力されたファイルをディレクトリにまとめる
