# techbook_base

OtakuAssemblyでの，技術同人誌のベースリポジトリ...になるやつ．
Re:VIEW 4.0を使用．

## ビルド方法

- Re:VIEWのインストール: `bundle install --path=vendor/bundle`

- PDFのビルド: `bundle exec review pdfmaker config.yml`
- EPUBのビルド: `bundle exec review epubmaker config.yml`
- HTMLのビルド: `bundle exec review webmaker config.yml`

## 執筆方法

- developから自分の原稿ブランチ(draft/username)を生やす
- catalog.ymlに自分の.reファイルを追加する
- article/username-hoge.reに原稿を書く
	- ファイルは複数にして大丈夫(というか分量が多い人は分割した方が良い)です
	- 先頭に自分のusernameをつけて誰のファイルか分かるようにしてね :heart:
- ある程度(数段落とか，数ページとか)書けたらdevelopにMRを飛ばす
- 他のオタク(基本的には編集担当)に見てもらう
- 大丈夫そうだったらdevelopにmerge

## 書く時・チェックする時の注意事項

- 想定読者を設定する(本文中に書いても良い)
- その文章は初めて読んだ(想定読者層の)人が理解できるようになっているか？

- CIをパスしているか？
- トンボから文章やソースコードがはみ出ていないか？
- トンボから文章やソースコードがはみ出ていないか？
- 画像は大丈夫か？
	- 位置は大丈夫？
	- モノクロで印刷されるけど大丈夫？
	- その文字の大きさで大丈夫？

- 一文がクソ長くなってない？
- 一段落がクソ長くなってない？
- てにをはは大丈夫か？
- 接続語は大丈夫？
- 専門用語の扱いは適切か？

- 1ページ当たりの情報量が薄すぎないか？
	- 紙はお金がかかります その金はオタクの金です
	- クソ長実装などは適宜GitHubとかに置いてリンクで参照するようにしましょう
- 内容の再現性はあるか？
	- 実行・開発環境などは書きましょう
	- Docker Imageなどになっていると天才です
- ちゃんとRe:VIEWの記法使ってる？
	- [フォーマットガイド](https://github.com/kmuto/review/blob/master/doc/format.ja.md)
	- 見出しはmdみたいにレベル分けできます
	- 用語をつらつらと並べていませんか？表とか用語リストとか使えます
	- ちょっと余談，みたいなのはコラムにすると本っぽくなります
	- 略語とかは適宜footnoteに突っ込んでいきましょう

## 何かしらの破壊的・複数人に影響を与える変更を行う場合

ディレクトリ構造を変えたくなったとか，Re:VIEWの設定を弄るとか，そういうやつ

- (draftブランチをdevelopに一旦merge)
- developから実験用のブランチを生やす(直接develop・master破壊push太郎は殺します)
- 大丈夫そうならdevelopにMR
- draftブランチでdevelopをmerge
