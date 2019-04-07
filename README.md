# cat-detector

## 概要

2015年に発行された「データサイエンティスト養成読本」の中の猫顔検出処理のサンプルコードを元に、実行できる環境として組み直したものです。

## 実行手順

### 学習

1. 正解画像となる猫顔画像を用意します。[ここ](https://www.kaggle.com/crawford/cat-dataset)などから顔情報のアノテーションのついた猫画像データセットがあるので取得するとよいです。その上で[元記事の著者のリポジトリ](https://github.com/t-abe/cat-face-detection)にある`crop_faces.py`を使用すると猫顔だけ切り出せるので便利です。同様に、適当な画像を1000枚ほど用意し`crop_negatives.py`を使用すると不正解画像を作れます。
2. 事前準備ができたら、以下の形でディレクトリ分けします。
   - `positive`: 学習用の正解画像フォルダ
   - `negative`: 学習用の不正解画像フォルダ
   - `positive_test`: 学習後のテスト用の正解画像フォルダ
   - `negative_test`: 学習後のテスト用の不正解画像フォルダ
3. `train.sh`を実行します。`ser_svm`というファイルができます。

### 検出実行

学習の最後に出力された`ser_svm`を使って認識を実行します。（引数指定は不要）

```
python detector.py some_image.jpg
```

これで、検出できるはずなんです、、、はず、、、
