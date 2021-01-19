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


<br>
<br>
<br>



## ◎深層学習　day4　S1　強化学習　<br>
### 講義内容の要点
#### (参考資料）最強囲碁AIアルファ碁解体新書<br>
　　　・強化学習とは、AI自身による成功体験を基に行動を改善していく仕組み。<br>
　　　　未知の情報を含む環境下での長期的な価値最大化を目指す。<br>
　　　・探索　…　「未知の情報を含む環境下での価値最大化」を図る（見つける）ための探索行動<br>
　　　・Q学習　…　下記行動価値関数を最大化するための学習行為。<br>
　　　・関数近似法　…　状態の数量が膨大な場合など計算負荷を下げるため関数近似を使用。<br>
　　　　-価値関数　…　強化学習で最大化を図る価値の関数で以下の2種類。<br>
　　　　　〇状態価値関数　…　状態の価値の関数<br>
　　　　　〇行動価値関数　…　状態と行動を併せた価値を表す関数<br>
　　　・方策関数　…　方策ベースの強化学習方法において、状態に対しとるべき行動を確率的に決定する関数<br>
　　　　-方策勾配法　…　方策ベースの学習手法で（行動価値関数ではなく）方策関数を使用<br>
<br>
<br>
<br>
## ◎深層学習　day4　S2　AlphaGo
### 講義内容の要点
#### (参考資料）最強囲碁AIアルファ碁解体新書<br>
　　　・ポリシーネットワーク　…　次の手の選択肢毎の確率を与える。<br>
　　　・バリューネットワーク　…　局面における勝敗確率を与える。<br>
　　　・ロールアウトポリシー　…　ロジスティック回帰により次の手の候補の確率を与える。<br>
　　　・ポリシーネットの教師あり学習　…　SLポリシーネットワーク。KGS Go Serverより3000万局分の教師データを使用<br>
　　　・ポリシーネットの強化学習　…　RLポリシーネットワー。強化学習過程500回毎の記録（PolicyPool）から抽出したものと対局シミュレーション。<br>
　　　・バリューネットの学習　…　CNNの予想勝率が学習データに近づくようしていく（学習する　）<br>
　　　・モンテカルロ木探索　…　通常のモンテカルロ法に、UCB1（勝率+バイアス）が大きくなる経路（打ち手）を選択する方法<br>
　　　・AlphaGo(Lee)とAlphaGo Zeroの違い　…　<br>
　　　　-ZeroはResidual Network(ResNet)構造を導入。<br>
　　　　-Zeroは学習に人間の対戦データは未使用（教師なし学習）。<br>
　　　　-ヒューリスティックを排除。<br>
　　　　-ポリシーネットワークとバリューネットワークを統合。<br>
　　　・ResidualNetwork　…　学習対象を「最適出力」から残差（Residual）関数へ。<br>
　　　・AlphaGo Zeroのモンテカルロ木探索　…　Rollout（Play Out…勝敗がわかる手まで試行を進めすこと）を不要とした<br>
　　　・AlphaGo Zeroの学習方法　…　AlphaGo Zero対AlphaGo Zeroの対戦（自己対局）で実施<br>
<br>
<br>
<br>
## ◎深層学習　day4　S3　データ並列化
　　　データを複数に分割し同一の数のモデルで処理。データが多いときに有効。<br>
　　　→同時に複数同一のモデルで処理されるので同一データ量の処理が単一で行うより時間が早まる。<br>
<br>　モデル更新のタイミングで同期型/非同期型に分類。→精度の良い同期型が昨今の主流。
<br>
<br>
## ◎深層学習　day4　モデル並列化
　　　同一のデータを複数のモデル（パラメータが異なる同一数理モデル）で処理。モデルサイズが大きいときに有効。<br>
　　　モデルパラメータ数が多いほど高速化。<br>
　　　・GPUの使用が有効（データ並列、モデル並列ともに有効）<br>
<br>
<br>
## ◎深層学習　day4　量子化
　　　・モデルの軽量化手法の一つ　…　重みの精度を落とし高速化と省メモリ化を図る<br>
<br>
<br>
<br>
## ◎深層学習　day4　蒸留
　　　・モデルの軽量化手法の一つ　…　教師モデルから単純化した軽量な生徒モデルを作成し使用。
　　　　精度の向上に貢献。<br>
<br>
<br>
<br>
## ◎深層学習　day4　プルーニング
　　　・モデルの軽量化手法の一つ<br>
　　　・重要度の低いニューロンを削除することにより高速化。<br>
　　　・ニューロンの削除は精度を落とす。<br>
<br>
<br>
<br>
## ◎深層学習　day4　MobileNet
　　　・ディープラーニングモデルの軽量化・高速化・高精度化<br>
　　　　→Depthwise ConvolutionとPointwise Convolutionで実現。
　　　・Depthwise Convolution　…　層間の畳み込みを行なわないので計算量小<br>
　　　・Pointwise Convolution　…　1×1の畳み込み。入力マップのポイント毎に畳み込みを実施。<br>
　　　・Depthwise Separable Convolution　…　上記のDepthwise ConvolutionとPointwise Convolutionの二つに分けて畳み込みを行う方法<br>
<br>
<br>
<br>
## ◎深層学習　day4　DenseNet
　　　・CNNの一種<br>
　　　・ResNetと似ているが、DenseNetでは各層からの出力が全ての後方層の入力となる（Densブロック）が、ReNetでは前1層の入力のみ後方の層へ入力。<br>
　　　・特徴マップの入力→Batch正規化→Relu関数による返還→3 x 3畳み込み層による処理　で出力を計算。<br>
　　　・growth rate　…　入力特徴マップのチャンネル数l×k,出力（l+1）×kとなるkの値<br>
<br>
<br>
<br>
## ◎深層学習　day4　BatchNorm
　　　・レイヤー間を流れるデータの分布を、ミニバッチ単位で平均が0・分散が1になるように正規化<br>
　　　・Batch Normalizationはニューラルネットワークにおいて学習時間の短縮や初期値への依存低減、過学習の抑制など効果。<br>
<br>
<br>
<br>
## ◎深層学習　day4　LayerNorm
　　　・それぞれのsampleの全てのpixelsが同一分布に従うよう正規化<br>
　　　・入力データのスケールに関してロバスト<br>
　　　・重み行列のスケールやシフトに関してロバスト<br>
<br>
<br>
<br>
## ◎深層学習　day4　InstanceNorm
　　　・channelも同一分布に従うよう正規化<br>
　　　・バッチサイズが1のBatch Normalizationに相当<br>
<br>
<br>
<br>
## ◎深層学習　day4　WaveNet　…　AlphaGp開発、2014Googleが買収
　　　・時系列データに対して畳み込みを適用する<br>
　　　・Dilated convolution　…　深い層のリンクを広げる。<br>
　　　・深層学習を用いて結合確率を学習する際に、効率的に学習が行えるアーキテクチャ<br>
<br>
<br>
<br>
## ◎深層学習　day4　Seq2Seq　…　翻訳、音声認識、チャットボット等で使用
　　　・Encorder-Decorder Model<br>
　　　・Transformer (Encorder-Decorder × Attention)<br>
　　　・BERT<br>
　　　・必要知識
　　　　-RNN<br>
　　　　-言語モデル　…　時刻t-1までの情報で、時刻tの事後確率を求めることが目標<br>
　　　　-ソフトマックス関数で最大化<br>
　　　<br>
　　　<br>
　　　<br>
　　　<br>
<br>
<br>
<br>
## ◎深層学習　day4　Transformer
　　　<br>
<br>
<br>
<br>
## ◎深層学習　day4　物体検知
　　　<br>
<br>
<br>
<br>
## ◎深層学習　day4　セグメンテーション
　　　<br>
<br>
<br>
<br>


