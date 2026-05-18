二桁の数字の偶奇判定

MNIST を用いて、2つの数字画像を左右に結合した「二桁画像」を作成し、その数が偶数か奇数かを判定する CNN モデルです。
PyTorch を用いて実装しています。

概要

通常の MNIST は 1 桁の数字画像ですが、このプロジェクトでは

2つの数字をランダムに選択
左右に結合して 2桁画像を生成
生成された二桁の数字が
偶数 → Even
奇数 → Odd

を分類するモデルを作成しています。

例：

左の数字	右の数字	二桁の数	ラベル
3	4	34	Even
5	7	57	Odd
使用技術
Python
PyTorch
torchvision
matplotlib
モデル構成

CNN（畳み込みニューラルネットワーク）を使用。

主な構成

Conv2D
ReLU
MaxPooling
全結合層
CrossEntropyLoss

データセット

MNIST を利用し、ランダムに2枚の画像を選択して結合。

入力画像サイズ：

1 × 56 × 28

（28×28 の画像を縦方向に2枚結合）

学習

学習設定
Optimizer : SGD
Loss : CrossEntropyLoss
Epoch : 100
Early Stopping 使用
可視化

学習後、

Loss Curve
CAM（Class Activation Map）

を用いてモデルがどこを見て判定しているかを可視化しています。

実行方法

ライブラリのインストール
pip install torch torchvision matplotlib


今後の改善

精度向上
横並び数字への対応
3桁以上への拡張
Transformer モデルとの比較
リアルタイム推論
