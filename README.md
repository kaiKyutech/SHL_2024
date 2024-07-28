# SHL_2024
SHLセンサデータセット(http://www.shl-dataset.org/)
を学習データにニューラルネットワーク構築  
**BESTModels**に作成したモデルの中で最高評価のものをまとめている。(開発モデルについて見るならここだけで良い)




# 以下開発メモ

# フォルダ構成（とメモ）    
### transformer   
BERT, DistilBertは実装できた。↓    
**my_neural_v25_distilBERT_3.ipynb**  
**my_neural_v19_BERT.ipynb**  
BERTは１つのセンサデータのみでの学習  
DistilBertは９つのセンサデータで学習した。  
  
nn.Embeddingsのところをnn.Linearに変えて８クラス分類を行った。マスクトレーニングなどはしていない。  
TST,TFTを実装予定  
TST(time series transformer)というモデルを見つけた。実装方法はまだよくわかっていない。  
### RNN  
**v14** にてLSTMを定義
またampが実装できたので高速化していると思う。  
v16_LSTM_lightningはまだ作成途中   
### resnet
resnetで学習  
**my_neural_v18_resnet18.ipynb**  が最も性能出ているモデル。  
### CNN_Alexnet 
独自で色々CNNを定義してみて学習させたもの。(Alexnet含む)  
v8だけはvalidationデータで評価してみたノートブック。  
バージョンが大きくなるにつれて新しく定義したもの  


## データ拡張について  
resnet v26にてデータの偏り除去は行った。
  
性能の改善はあまりできてなかった。  
次はデータ拡張を試すとよいかも。


# アンサンブル学習について  
以下のものを少しずつ試していく。  
フォルダはensambleで
バギング: 複数のモデルを並列に訓練し、予測を平均または多数決で組み合わせる。
ブースティング: 弱学習器を連続的に訓練し、誤分類されたサンプルに重点を置く（例：XGBoost、AdaBoost）。
スタッキング: 複数のモデルの予測を新しい特徴量として使用し、最終的な予測を行うメタモデルを訓練する。

# ハイパーパラメータチューニング
グリッドサーチ: 事前に定義したハイパーパラメータの組み合わせを全て試す。
ランダムサーチ: ランダムに選ばれたハイパーパラメータの組み合わせを試す。
ベイズ最適化: ハイパーパラメータ空間を探索するためのベイズ推論を使用する。