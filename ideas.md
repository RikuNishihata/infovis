
# アイデアなど
## クローラーとスクレイパー
- スクレイパーの入出力
	- 入力：URL（str）<br>
	- 出力：[サイズの数(int), [商品名, サイズ, 値段, ウエスト, もも周り, すそ], [], ...]

```:python
#出力例
[5,
 ['別注 ISCHIA コーデュロイ 1プリーツ イージーパンツ', '42', '24200', '76.5', '60.0', '95.0'],
 ['別注 ISCHIA コーデュロイ 1プリーツ イージーパンツ', '44', '24200', '81.5', '61.5', '97.5'],
 ['別注 ISCHIA コーデュロイ 1プリーツ イージーパンツ', '46', '24200', '84.5', '62.5', '104.0'],
 ['別注 ISCHIA コーデュロイ 1プリーツ イージーパンツ', '48', '24200', '87.5', '67.0', '105.5'],
 ['別注 ISCHIA コーデュロイ 1プリーツ イージーパンツ', '50', '24200', '91.5', '68.5', '111.0']]
```
- 商品を色で区別する（としたらその）ときのスクレイパーの呼び出しはどうするか．色ごとに行う or 各商品に対して一度のみ（<-こっちのほうが良さそう）
- データ数が少ない．余裕があるならZOZOTOWNからもデータを取ったら良さそう．<- 確認したところbeamsのときと同じ要領でできそう．

## csvファイルの書式
- データセットの形式（暫定）：商品ID，名前，金額，ウエスト，もも，すそ，商品ページURL
<br>
↑ 色も追加したほうが良さそう．その場合の型は？ eg.文字列/RGB

## プロット用のHTMLを作る
プロットは，すその大きさを横軸に，ももの大きさを縦軸に取る

- プロットする円の大きさは？
	- とりあえず5にしている。
- プロットする円の色は？
	- とりあえず青にしている。

## 追加機能の表示

- 詳細情報の表示について
	- 図上の青点をクリックすると，それに対応する商品の取り込んだデータの情報を最低限の文字として表示するところまでは出来ている。
	- URLの埋め込みも出来た。

## ズームイン・ズームアウト機能の追加

- 具体的にどのような機能が追加されるか？
	- Google Mapのようなものを想定している
- 実装の方法は？

## パンツのサイズ調整

- すそともも，それぞれを動かし，それに連動して図上の赤点も動くような仕様は出来た。


# todoリスト
## 11/4(木)
- 小規模なデータセットを作る（簡単なもの）→プロットを作る
	- 4つのデータセットを作り，それに対しての最低限のプロット機能は出来た。
- クローラを完成させる
- スクレイパーを完成させる -> 形にはなった
- データセットに対してのプロットを行う
	-csvファイルを読み込み，最低限のプロットを行うところまでは出来た。

## 11/8(月)
- 既存のデータセットにズームイン・ズームアウト，追加機能の表示，パンツのサイズ調整の3つの機能を追加する(QRA5)
- 出来次第，HTMLの方にもこれらの機能を追加する

## 11/11(木)
- 「ズボンの絵を動かすと」「自分の位置が表示され」「商品をクリックすると詳細情報が表示される」という，当初に予定していた必要最低限の機能は現時点で出来ている。
- 詳細情報について
	- URL埋め込みも出来た。
- 未実装の機能
	- 金額、ウエスト、色での絞り込み
	- 散布図上で重なっている要素をどうクリックするか 
	- クリックしたときにその寸法を図にして表示する

## 11/15(月)
- デモ完成
	- 金額や商品属性でフィルタリングできるようになった．
	- 商品画像を表示できるようになった

-追加で実装できたら嬉しいこと
	- フィルタリングをより直感的に（brushXを用いた金額フィルタリングや画像付きボタン）
	- ページがやや味気ない..?
