***
>### [3か月で現場で潰しが効くディープラーニング講座][1]
>[1]:http://study-ai.com/jdla

>![alt](http://ai999.careers/bnr_jdla.png)
***

# E資格取得のための学習内容レポート

<br>

### 　（使用したその他参考資料）
　　・ゼロから作るDeep Learning　フレームワーク編<br>
　　・ゼロから作るDeep Learning　自然言語処理編<br>
　　・最強囲碁AIアルファ碁解体新書<br>
　　<br>


## ◎深層学習　day4　S1　強化学習　<br>
### 講義内容の要点
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
　　・ポリシーネットワーク　…　次の手の選択肢毎の確率を与える。<br>
　　・バリューネットワーク　…　局面における勝敗確率を与える。<br>
　　・ロールアウトポリシー　…　ロジスティック回帰により次の手の候補の確率を与える。<br>
　　・ポリシーネットの教師あり学習　…　SLポリシーネットワーク。KGS Go Serverより3000万局分の教師データを使用<br>
　　・ポリシーネットの強化学習　…　RLポリシーネットワー。強化学習過程500回毎の記録（PolicyPool）から<br>
　　　抽出したものと対局シミュレーション。<br>
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
　　・データを複数に分割し同一の数のモデルで処理。データが多いときに有効。<br>
　　　→同時に複数同一のモデルで処理されるので同一データ量の処理が単一で行うより時間が早まる。<br>
　　・モデル更新のタイミングで同期型/非同期型に分類。→精度の良い同期型が昨今の主流。<br>
<br>
<br>
## ◎深層学習　day4　モデル並列化
　　　同一のデータを複数のモデル（パラメータが異なる同一数理モデル）で処理。モデルサイズが大きいときに有効。<br>
　　　モデルパラメータ数が多いほど高速化。<br>
　　　・GPUの使用が有効（データ並列、モデル並列ともに有効）<br>
<br>
<br>
## ◎深層学習　day4　GPUによる高速化
　　・CUDAが一般的。（AI以外だがOpenCL使用という話をほとんど聞いたことがない）<br>
　　・同じNVIDIA社のGPUでも製品によりメモリ量、Capabilityが異なるため、使用する製品に合わせた設計が必要。<br>
　　・単純な並列処理であればCPUよりも圧倒的な高速化が可能。<br>
　　・高速化のためのチューニングは熟練が必要。<br>
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
　　　→Depthwise ConvolutionとPointwise Convolutionで実現。<br>
　　・Depthwise Convolution　…　層間の畳み込みを行なわないので計算量小。<br>
　　・Pointwise Convolution　…　1×1の畳み込み。入力マップのポイント毎に畳み込みを実施。<br>
　　・Depthwise Separable Convolution　…　上記のDepthwise ConvolutionとPointwise Convolutionの二つに分けて畳み込みを行う方法<br>
<br>
<br>
<br>
## ◎深層学習　day4　DenseNet
　　・CNNの一種<br>
　　・ResNetと似ているが、DenseNetでは各層からの出力が全ての後方層の入力となる（Densブロック）が、<br>
　　　ReNetでは前1層の入力のみ後方の層へ入力。<br>
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
　　・Seq2Seq必要知識
　　　-RNN、<br>
　　　-言語モデル　…　時刻t-1までの情報で、時刻tの事後確率を求めることが目標<br>
　　　-ソフトマックス関数で最大化<br>
　　・RNN　×　言語モデル<br>
　　　-(時)系列情報を内部状態に変換<br>
　　　-文章に各単語が現れる同時確率→事後確率で分解可。→事後確率の算出がRNNの目標<br>
　　　-言語モデルの再現をRNNで重み学習→次の単語予測を可能とする。→先頭単語から文章作成も可能。<br>
　　・Seq2seq<br>
　　　-encorderからdecorderへ渡される内部状態ベクトルがキーポイント<br>
　　　-decorderの構造はRNNとほぼ同じ<br>
　　　-decorderの初期値はencorder側の内部状態<br>
　　　-decorderの出力側に正解を持ってきて比較。→教師あり学習がend2endで可能。<br>
　　・実装演習
　　　（省略）
<br>
<br>
<br>
## ◎深層学習　day4　Transformer
　　・Self-Attention(自己注意機構)　…　同一時系列内のAttention。<br>
　　・Atention　…　重要なものの重みを大きくする重要でないものは小さく学習していく。<br>
　　　-query　…　入力からくる検索対象
　　　-key　…　queryとの関連計測の索引
　　　-Value　…　キーの結果出力される値
　　・Encorder-Decorderモデルは長い文章に弱い→Atentionで対応。<br>
　　・ソースターゲット注意機構　…　入力Queryと索引が別物。<br>
　　・自己注意機構　…　入力Queryと索引が同じ。<br>
　　・Position-Wise Feed-Forward Networks　…　位置情報を保持したまま順伝搬。<br>
　　・Scqled dot product attention　…　前タンゴに関するattentionをまとめて計算。<br>
　　・Multi-Head attention　…　重みパラメタの異なる8個のヘッド。<br>
　　・Decorder　…　Encorderと同じ6層。Attentionは両方あり。
　　・Add & Norm　…　学習効率化テクニック<br>
　　・Position Encoerding　…　RNNを用いない為単語の語順情報追加<br>
　　・実装演習
　　　（省略）
<br>
<br>
<br>
## ◎深層学習　day4　物体検知
　　・分類　…　クラスラベル<br>
　　・物体検知　…　BB<br>
　　・意味領域分割　…　クラスラベル<br>
　　・個体領域分割　…　クラスラベル<br>
　　・代表的なデータセット<br>
　　　-VOC12　…　PASCAL VOC Object Detection Challenge。主要貢献者が2012年に亡くなったことに伴いコンペも終了。<br>
　　　-ILSVRC17　…　ImageNet（21,841クラス/1400万枚以上）のサブセット。<br>
　　　　コンペは2017年に終了（後継：Open Images Challenge）。<br>
　　　-MS COCO18　…　物体位置推定に対する新たな評価指標を提案。<br>
　　　-OICOD18　…　ILSVRCやMS COCOとは異なるannotation process。Open Images V4（6000クラス以上/900万枚以上）のサブセット<br>
　　・評価指標<br>
　　　-Confusion Matrix　…　機械学習の項参照<br>
　　　-IoU　=TP/(TP+FP+FN)　別名Jaccard係数<br>
　　　-AP：Average Precision　…　=∫P(R)dR　(0≦R≦1)<br>
　　　-mAP：mean Average Precision　…　APの平均値<br>
　　　-FPS：Flames per Second　…　単位秒あたりの処理枚数<br>
　　・物体検知の大枠　…　-2012年AlexNetの登場を皮切りに, 時代はSIFTからDCNNへ<br>
　　・物体検知のフレームワーク<br>
　　　-２段階検出器（Two-stage detector）　…　候補領域の検出とクラス推定を別々に行う。低速、精度高<br>
　　　-１段階検出器（One-stage detector）　…　候補領域の検出とクラス推定を同時に行う。高速、精度低<br>
　　・SSD　…　Default Boxを（検知物体に合わせ）変形しconf.を出力。<br>
　　　-ネットワークアーキテクチャ<br>
　　　　〇マルチスケール特徴マップ<br>
　　　　　□入力　SSD300、SSD512<br>
　　　　　□VGG16の10層目相当の畳み込み層<br>
　　　　　□VVGG16のFC2層は畳み込み層に変更<br>
　　　-多数のDefault Boxを用意したことで生ずる問題への対処<br>
　　　　〇Non-Maximum Suppression<br>
　　　　〇Hard Negative Mining<br>
　　　-損失関数　L(x, c, l, g) = 1/N × (L_conf(x, c) + α×L_loc(x, l, g))　L_conf(x, c)：confidenceに対する損失、L_loc(x, l, g)：検出位置に対する損失<br>
　　・<br>
　　・<br>
<br>
<br>
<br>
## ◎深層学習　day4　セグメンテーション
　　・FCN for Semantic Segamentation　…　FCNはSemantic Segamentationの様に、”ピクセル単位のタスクの高密度予測”を学ぶことができる<br>
　　・Deconvolution/Transposed convolution　…　unsampling<br>
　　　-通常のConv.層と同様, Kernel size, padding, strideを指定<br>
　　　-逆畳み込みとも呼ばれる。<br>
　　　-畳み込みの逆演算ではない。<br>
　　　-poolingにより失われた輪郭情報を補完<br>
　　・U-NET　…　効果的なデータ増量方法<br>
　　・SegNet　…　Encoderで特徴量抽出。Decorderでラベリング<br>
　　・DeconvNet　…　畳み込み層とmax-pooling層を交互に重ねる<br>
　　・Dilated Convolution　…　畳み込みの段階で受容野を広げる工夫<br>
<br>
<br>
以上<br>


