# SHL_2024
センサデータを学習データにニューラルネットワーク構築  
その実践学習  

# フォルダ構成（とメモ）    
### transformer   
BERT, DistilBertは実装できた。↓    
**my_neural_v25_distilBERT_3**  
**my_neural_v19_BERT**  
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
**v18_resnet18**  が最も性能出ているモデル。  
### CNN_Alexnet 
独自で色々CNNを定義してみて学習させたもの。(Alexnet含む)  
v8だけはvalidationデータで評価してみたノートブック。  
バージョンが大きくなるにつれて新しく定義したもの  


## データ拡張について  
データの偏りについてこれまで考慮せずに学習を行ってきた。未だに実装していない。急務！  
ノイズを加えたり、アンダーサンプリングしたり色々あるみたい  

# アンサンブル学習について  
