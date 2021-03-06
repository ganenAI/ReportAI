﻿***
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

## ◎深層学習　day1　S1　入力層～中間層
### 講義内容の要点

　　・NNでできること

　　　-回帰（結果予想、ランキング等）

　　　-分類（文字認識、画像判別等）

　　・入力層…説明変数等、外部からデータを取り込む機能。取り込んだデータはそのまま中間層へ引き渡す（重みをかけバイアス項を加算して渡す？）。

　　・中間層…各種処理（この講義内では詳細説明なし）


### 確認テスト1
　　ディープラーニングは、結局何をやろうとしているか2行以内で述べよ。<br>また、次の中のどの値の最適化が最終目的か。全て選べ。（1分）<br>　　　①入力値[ X]<br>　　　②出力値[ Y]<br>　　　③重み[W]<br>　　　④バイアス[b]<br>　　　⑤総入力[u] <br>　　　⑥中間層入力[ z]<br>　　　⑦学習率[ρ]NN全体像確認テスト

　　＜回答＞<br>
　　　やろうとしていること：入力データから最適な出力となるパラメータを発見する。<br>
　　　最終目的：③重み、④バイアス
<br>
　　　
### 確認テスト2
　　次のネットワークを紙にかけ。<br>　　　入力層︓2ノード1層<br>　　　中間層︓３ノード2層<br>　　　出力層︓1ノード1層（5分）
　　＜回答＞<br>
![alt](https://user-images.githubusercontent.com/77253188/104692354-2cc1e380-574b-11eb-8ca6-057416547cee.png)

<br>

### 確認テスト3
　　（略）
<br>
<br>
<br>


## ◎深層学習　day1　S2　活性化関数
### 講義内容の要点

　　・活性化関数とは

　　　次の層への出力の大きさを決定する非線形関数。

　　・中間層で使用する活性化関数

　　　-ReLU関数　…x(x>0)、0(x≦0)

　　　-シグモイド関数　（機械学習の頁参照）

　　　-ステップ関数　…　１(x≧0）、　0（x<0)）

　　・出力層の活性化関数（詳細は深層学習　S3　出力層の項参照）

　　　-ソフトマックス関数

　　　-恒等写像

　　　-シグモイド関数

　　・全結合

　　　上位層と回想の全ノード間で結合

<br>

### 確認テスト5
　　線形…変数間が線形結合

　　非線形…変数間が非線形結合

<br>
<br>
<br>

## ◎深層学習　day1　S3　出力層
### 講義内容の要点

　　・役割

　　　中間層から受け取った結果を比較対象（訓練データ）と比較し中間層での処理状態を判定する。

　　　-誤算関数…訓練データと中間層からの出力値との差分の関数（種類はいくつか存在）<br>
　　　　平均二乗誤差、クロスエントロピー誤差等。

　　・活性化関数

　　　-中間層との相違点<br>
　　　　〇信号の大きさは無変換<br>
　　　　〇出力ノードの合計が必ず1とする<br>
　　　　〇中間層で記述済のように使用する活性化関数の種類が異なる<br>
　　　　〇出力層の活性化関数（

　　　　　◇ソフトマックス関数　f(i,u)=exp(u(i))/Σ(exp(u(k))、誤差関数は交差エントロピー

　　　　　◇恒等写像　f(u)=u、誤差関数は二乗誤差

　　　　　◇シグモイド関数　f(u)=1/(1+exp(-u))、誤差関数は交差エントロピー


<br>

### 確認テスト5
　　・なぜ、引き算でなく二乗するか述べよ<br>・下式の1/2はどういう意味を持つか述べよ（2分）

　　＜回答＞

　　　・プラスもマイナスも同等に罰則を与えるため。<br>
　　　・微分したとき計算をしやすくするため。

<br>

### 確認テスト7
　　・なぜ、引き算でなく二乗するか述べよ<br>・下式の1/2はどういう意味を持つか述べよ（2分）

　　＜回答＞

　　　・プラスもマイナスも同等に罰則を与えるため。<br>
　　　・微分したとき計算をしやすくするため。

<br>
<br>
<br>


## ◎深層学習　day1　S4　勾配降下法
### 講義内容の要点

　　・目的

　　　勾配降下法を使用してパラメータ最適化を図る。（下記ｗを調整しEが最小となる点を探る）

　　　w(t+1)=w(t)-ε∇E, ∇E＝∂E(w)/∂w, ε：学習率…収束のスピード/精度（トレードオフ）を調整

　　・学習率決定のアルゴリズム

　　　-Momentum	

　　　-AdaGrad

　　　-Adadelta	

　　　-Adam	

　　・確率的勾配降下法

　　　ランダムに抽出したサンプルデータのみ使用して誤差計算を行う。→計算負荷軽減、局所解を避ける、オンライン学習

　　・ミニバッチ勾配降下法

　　　ランダムに分割したデータ内の平均誤差を計算。→計算負荷軽減。並列処理（分割したものを同時平行に処理）

　　・数値微分…実務的には計算負荷が大きいため使用されない。
<br>
#### （金融実務的観点）<br>
　　近年金融分野でもAD乃至AAD（所謂自動微分）が一部導入（AI以外だが）されてきたが、＜br＞その実装負荷の大きさから導入実績は限られる。このため実装負荷の小さい（計算負荷は大）数値微分（Bumping）はいまだ多用されている。
<br>
<br>確率的勾配法による収束状況
![alt](https://user-images.githubusercontent.com/77253188/104722757-ac62a900-5771-11eb-8f6a-6c3030fe6375.png)

<br><br><br>


## ◎深層学習　day1　S5　誤差逆伝搬法
### 講義内容の要点

　　テキストに記載はないが所謂AD(自動微分）の手法。微係数を連鎖率を使用して計算する。<br>
　　原理的には前進と後進があり、誤差逆伝搬法は後進を使用。

<br>

### 確認テスト8

オンライン学習はデータ到来毎に処理を実施する。

<br>
<br>
<br>

## ◎深層学習　day2　S1　勾配消失問題
### 講義内容の要点

　　・誤差逆伝搬処理を継続していると勾配が緩やかになり最適解に収束しなくなる。

　　・シグモイド関数で発生。→　ReLU関数で解決。

　　**・ニュートン・ラフソン系の処理は初期値が重要**

　　　-Xavierの初期値設定→前のノード数の平方根

　　　-Heの初期値設定→前のノード数の平方根×√2

　　・バッチ正規化　…　ミニバッチ単位で実施。

<br>
![alt](https://user-images.githubusercontent.com/77253188/104718819-da92b980-576e-11eb-8c52-79c7342b8885.png)


<br>

### 確認テスト9？連鎖率

　　＜回答＞<br>　
　　　dz/dt=2t<br>
　　　dt/dx=1<br>
　　　より<br>
　　　dz/dx=dz/dt*dt/dx=2t<br>
<br>
### 確認テスト10？　シグモイド関数の微分値
　　＜回答＞<br>
　　　0.5*（1-05）＝0.25　(2)が正解<br>
<br>
### 確認テスト11？　パラメータ初期値
　　＜回答＞<br>
　　　説明変数にゼロが乗算されるので、全てゼロ+定数項の値になりパラメータ推定不能となる。<br><br>

### 確認テスト12？　バッチ正規化
　　＜回答＞<br>
　　　・計算結果のブレを抑える<br>
　　　・高速化<br>
<br><br><br>



## ◎深層学習　day2　S2　学習率最適化手法
### 講義内容の要点

　　・学習率の決定方法→学習率最適化手法を使用<br>
　　　
　　　-モメンタム	…　Ⅴ(t)=μV(t-1)-ε∇E　⇒　W(t+1)=W(t)-ε/（√h(t)+θ）×∇E<br>
　　　　大域的最適解<br>
　　　　最適地への到達が速い<br>

　　　-AdaGrad		…　h0=θ　⇒　h(t)=h(t-1)+(∇E)^2　⇒　W(t+1)=+V(t)<br>
　　　　緩やかな勾配でも解を発見できる<br>

　　　-RMSProp		…　h(t)＝αh(t-1)+(1-α)(∇E)^2　⇒　W(t+1)=W(t)-ε/（√h(t)+θ）×∇E<br>
　　　　大局的最適解<br>
　　　　ハイパーパラメータの調整負荷小<br>

　　　-Adam			…	モメンタムとRMSPropの指数関数的減衰平均（RMSPropは2乗）を含んだもので、両者の長所を併せ持つ。<br>
　　　　

<br><br>

### 確認テスト13？　学習率最適化手法
　　＜回答＞<br>
　　　・モメンタム	… 大域的最適解で最適値への到達が速い。
　　　・AdaGrad		… 緩やかな勾配でも解を発見できる。
　　　・RMSProp		… 大域的最適解でハイパーパラメータの調整負荷が小。<br>
<br>

### プログラム実装　学習率の最適化手法

![alt](https://user-images.githubusercontent.com/77253188/104715382-d6b06880-5769-11eb-86dd-4588819a11e4.png)

<br><br><br>

## ◎深層学習　day2　S3　過学習
### 講義内容の要点

　　・正則化<br>
　　　-L1正則化　…　機械学習の項で学習済み<br>
　　　-L2正則化　…　機械学習の項で学習済み<br>
　　　-ドロップアウト　…　ランダムにノードを削除し学習<br>
　　・Weight decay（荷重減衰）<br>
　　　誤差に対し正規化項を加え重みを抑制<br>
<br>
<br>
### 確認テスト14？　正則化
　　＜回答＞<br>
　　　(a)<br>
　
### 確認テスト15？　L1,L2正則化
　　＜回答＞<br>
　　　右側<br>
<br>

![alt](https://user-images.githubusercontent.com/77253188/104719565-04001500-5770-11eb-9b29-1f8d5c5b6504.png)


<br>
<br>
<br>

## ◎深層学習　day2　S4　畳み込みニューラルネットワークの概念
### 講義内容の要点

　　・畳み込み層<br>
　　　-バイアス入力値にフィルタをかけ、出力された値とバイアス項で活性化関数を計算する処理を行う。<br>
　　　-パディング　…　入力データの外周に人工的に値を設定。<br>
　　　-ストライド　…　フィルタの移動幅<br>
　　　-チャンネル　…　入力データの3次元目<br>
　　・プーリング層<br>
　　　対象領域のMaxまたは平均を取得する<br>
<br>
<br>
### 確認テスト16？　畳み込み
　　＜回答＞<br>
　　　(6-2)+1＝5<br>
　　　出力サイズは5×5//<br>
<br>
<br>
<br>
## 深層学習　day2　S5　最新のCNN
### 講義内容の要点

　　・AlexNet<br>
　　　-5層の畳み込みとプーリング層+3層の全結合層<br>
　　　-過学習を防ぐためサイズ4096の全結合層の出力にドロップアウト使用<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
