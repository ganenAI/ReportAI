***
>### [3か月で現場で潰しが効くディープラーニング講座][1]
>[1]:http://study-ai.com/jdla

>![alt](http://ai999.careers/bnr_jdla.png)
***

# E資格取得のための学習内容レポート

<br>

### 　（使用したその他参考資料）
　　・ゼロから作るDeep Learning　フレームワーク編<br>
　　・深層学習（近代科学社）<br>
　　・深層学習（講談社）<br>
　　<br>

## ◎深層学習　day3　S1　再帰型ニューラルネットワークの概念
### 講義内容の要点
　　・RNN　…　時系列データ対応の<br>
　　・時系列データ　…　過去データを日次や月次等で保有するデータ。相互に統計的依存関係あり<br>
　　　　**金融分野では株や為替、金利等の時系列データが頻繁に使用される**<br>
　　・再帰構造（出力データのフィードバック）<br>
　　・BPTT　…　Back Propagation Thorough Time <br>
　　　　　　　　時間軸のバックプロパゲーション（逆伝搬）
<br>
<br>
　　＜Simple RNN実行結果図＞<br>
![alt](https://user-images.githubusercontent.com/77253188/104731883-b4294a00-577f-11eb-8766-7c35919b2391.png)<br>
<br>

### 確認テスト？　畳み込み
　　＜回答＞<br>
　　　2×2<br>
<br>
### 確認テスト？　RNNの重み
　　＜回答＞<br>
　　　時系列（時間軸）移動の重み<br>
<br>
### 確認テスト？　RNNの処理
　　＜回答＞<br>
　　　dz/dt=2t<br>
　　　dt/dx=1<br>
　　　dz/dx=dz/dt * dt/dx =2t//<br>
<br>
### 確認テスト？　連鎖率
　　＜回答＞<br>
　　　u1=w(in)*x1 + w*z0+b
　　　z1=g(u1)<br>
　　　v1=w(out)*z1+c<br>
　　　y1=g(w(out)*z1+c)<br>
　　　　=g(w(out)*g(w(in)*x1 + w*z0+b)+c)//<br>

<br>
<br>
<br>
## ◎深層学習　day3　S2　LSTM
### 講義内容の要点
　　・LSTMは勾配消失問題への対処策。<br>
　　　しかしday2までに行ったものとは別のもの。<Br>
　　・CEC　…　過去データを保存<br>
　　・入出力ゲート　…　重みの計算を行えるようにする<br>
　　・忘却ゲート　…　不要な過去データ削除<br>
　　・覗き穴結合　…　CEC自身の値に、重み行列を介して伝播可能にした構造。<br>
<br>
<br>

### 確認テスト？　シグモイド微分値最大
　　＜回答＞<br>
　　　（２）<br>
### 確認テスト？　LSTM
　　＜回答＞<br>
　　　　出力<br>
<br>
<br>
<br>
## ◎深層学習　day3　S3　GRU
### 講義内容の要点
　　・GRUはLSTMのパラメータ数を大幅に削減<br>
<br>
<br>

### 確認テスト？　LSTNMとCECの問題
　　＜回答＞<br>
　　　LSTM…不要な情報の蓄積<br>
　　　CEC…重みが一律<br>
### 確認テスト？　LSTNMとGRUの違い
　　＜回答＞<br>
　　　パラメータ数<br>
　　　<br>
<br>
<br>
## ◎深層学習　day3　S4　双方向RNN
### 講義内容の要点
　　未来の情報も加味する。<br>
<br>
<br>
<br>
## ◎深層学習　day3　S5　Seq2Seq
### 講義内容の要点
　　Encoder-Decorderモデルの一種。<br>
　　用途として機械翻訳等<br>
　　・Encorder RNN　…　トークン毎に分割し処理。<br>
　　・Decorder RNN　…　トークン毎にアウトプットを作成。<br>
　　・HRED　…　過去n-1 個の発話から次の発話を生成する。文脈の考慮<br>
　　・VHRED　…　HREDに、VAEの潜在変数の概念を追加したもの。<br>
　　　　　　　　VAE：Variational Autoencoder<br>
　　・オートエンコーダ　…　教師なし学習の一つ<br>
　　・VAE　…　潜在変数zに確率分布z∼N(0,1)を仮定したもの<br>
<br>
<br>
<br>
### 確認テスト？　Seq2Seq
　　＜回答＞<br>
　　　(2)<br>
### 確認テスト？　seq2seqとHRED、HREDとVHREDの違い
　　＜回答＞<br>
　　　前者は文脈考慮能力、後者はVAEの考慮有無<br>
### 確認テスト？　VAE
　　＜回答＞<br>
　　　標準正規分布<br>
<br>
<br>
<br>
## ◎深層学習　day3　S6　Word2vec
### 講義内容の要点
　　学習データからボキャブラリを作成<br>
　　・one-hot ベクトル　…　大規模データの分散表現の学習が、現実的な計算速度とメモリ量で実現可能<br>
<br>
<br>
<br>
## ◎深層学習　day3　S7　Attention Mechanism
### 講義内容の要点
　　入力と出力のどの単語が関連しているのか」の関連度を学習する仕組み。<br>
<br>
<br>
### 確認テスト？　RNNとword2vec、seq2seqとAttentionの違い
　　＜回答＞<br>
　　　前者はぼきゃぶtらり作成有無、単語間の関連度の学習有無<br>
<br>
<br>
<br>

predict sin　計算結果図
![alt](https://user-images.githubusercontent.com/77253188/104737527-b55e7500-5787-11eb-961f-bd5faa0849d0.png)<br>





