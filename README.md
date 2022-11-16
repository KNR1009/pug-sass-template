# プロジェクト名

- プロジェクトの説明

## 使用技術

- pug([pug の書き方](https://qiita.com/takeshisakuma/items/fdcf456d8250e6dafc7b))
- sass([sass の書き方](https://qiita.com/nchhujimiyama/items/8a6aad5abead39d1352a))
- jQuery ([jQueryの書き方](https://www.kagoya.jp/howto/it-glossary/web/jquery/))
- [gulp.js](https://gulpjs.com/)

## 開発環境

```
$ cd src
# パッケージのインストール(初回のみ)
$ yarn
# ローカル環境の立ち上げ
$ yarn gulp
```
http://localhost:3000/ が立ち上がればOKです

## CSS 設計について

- クラス名は BEM を採用 ([BEMを使った書き方についてまとめてみた](https://qiita.com/takahirocook/items/01fd723b934e3b38cbbc))
- CSS設計は[FLOCSS](https://qiita.com/super-mana-chan/items/644c6827be954c8db2c0)を採用

## ディレクトリ構成

### pug/xxx

HTML(pug)を記述していくディレクトリになっています。
最終的に index.pug にコンポーネントやレイアウトファイルを読み込ませて出力させています。

### pug/xxx/Object

この中に component(ボタンなどの小さい単位)たプロジェクト(セクションごとの単位)を格納して、最終的に index.pug にて読み込んでいます。
ファイル名に関しては、コンポーネントの場合は「c-xx」で、プロジェクトの場合は「p-xx」と命名してください。

### sass/xxx/

FLOCSS 設計で構成されています。

/fundation は共通ファイルなので基本いじらない(h1,h2 などのリセット css など)
/object は pug で命名したものと同じ。ここにコンポーネントやプロジェクトのスタイルを当てていきます

書くファイルごとに\_index.scss というエントリーポイントがあるので、こちらに読み込みを行ってください。
最終的には/sass/style.scss に全てのディレクトリのエントリーポイントファイルを読み込んでいきます

### js/script.js

jQuery ファイルを読み込んでいます。(あんまりない)

### images/xxx

画像は全てこちらに格納してください。

## 納品形式

納品は html ファイルとして提出するので出力されたファイルをディレクトリにまとめる
