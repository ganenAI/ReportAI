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

## 機械学習　第1章　線形回帰
### 講義内容の要点

　　・回帰モデルとは、1個以上の説明変数からスカラー地の目的変数を予測するもの。

　　・線形回帰は説明変数間を線形結合+切片にて、説明変数を算出する。

　　・線形回帰…説明変数間が線形結合

　　・非線形回帰…説明変数間が非線形結合

　　・単回帰…説明変数が一つ

　　・重回帰…説明変数が複数

　　・連結方程式を解いてパラメータ（回帰係数）の値を求める（最小二乗法）

### ハンズオン（課題の回答は以下の通り）

　　●設定<br>　　　○ボストンの住宅データセットを線形回帰モデルで分析<br>　　　○適切な査定結果が必要<br>　　　　■高すぎても安すぎても会社に損害がある<br>　　●課題<br>　　　○部屋数が4で犯罪率が0.3の物件はいくらになるか？

　　＜回答＞

　　回帰係数は、

　　・CRIM　-0.265

　　・RM　8.391

　　・切片　-29.245　

　　部屋数4、犯罪率0.3のPrice=-0.265×0.3+8.391×4＝4.24

　　**回答　4.24**

　　係数算出の画像は以下。
![alt](https://user-images.githubusercontent.com/77253188/104410461-bb97fa00-55ab-11eb-9d99-35838dffb830.png)

<br><br><br>

## 機械学習　第2章 非線形回帰モデル
### 講義内容の要点

　　・基底展開法

　　　yi=wo+Σ(wj×φj(xi))+εi,　φj(xi)：基底関数…非線形関数

　　　パラメータ（上記wi）の推定は線形回帰と同等。

　　・留意事項

　　　未学習と過学習

　　　正規化法：過学習への対処法として、モデルの複雑さに罰則校を追加

　　　正規化法の分類

　　　　Ridge推定量…L2ノルム　

　　　　Lasso推定量…L1ノルム　パラメータのいくつかはがゼロとなるケースあり

　　・汎化性能

　　　汎化誤差を小さくし、汎用性を高める。

　　　-ホールドアウト法

　　　　取得したデータを検証用と学習用の二つに分ける。

　　　-クロスバリデーション

　　　　①取得したデータを複数個のに分け、検証用１個と残りを学習用としモデル作成。

　　　　②検証用を学習用として使用したデータに変更しモデル作成。

　　　　③上記の①,②を繰り返す（ただし同じテータ群を二度検証用とはしない）。

　　　


- サンプルデータでのLasso,Ridge処理比較確認
![alt](https://user-images.githubusercontent.com/77253188/104445192-2e20ce00-55dc-11eb-8f6a-a1f6ad9aed73.png)


<br><br><br>

## 機械学習　第3章 ロジスティック回帰モデル
### 講義内容の要点

　　・ロジスティック回帰は複数の説明変数から、0　or　１の値を取り出し、判定する。<br>
　　　（私の経験では、企業のデフォルト確率の算出（0か１ではなく確率）にこのロジスティック回帰を使用）

　　・シグモイド関数σ(x)

　　　σ(x)=1/(1+exp(-ax))

　　　∂σ(x)/∂x=aσ(x)(1-σ(x))

　　・最尤推定

　　　尤度関数を最大化するパラメータを求める。

　　　ロジスティック回帰の回帰係数を最尤推定にて算出。

　　　-勾配降下法

　　　　w(k+1)=w(k)-η×∂E(w)/∂w　　…(ニュートン法にηを追加した手法に相当)

　　　　更新終了は勾配ゼロ地点到達を意味する。

　　　-確率的勾配降下法（SGD)

　　　　説明変数のデータを確率的に選択し、計算負荷を下げる方法。

　　・混同行列（confusion matrix）

　　　モデルの予測について以下分類する

　　　True Positive(TP)		…正しくPositiveを予測<br>
　　　False Negative(FN)	…誤ってNegativeを予測<br>
　　　False Positive（FP)	…誤ってPositiveを予測<br>
　　　True Negative（TN)	…正しくPositiveを予測

　　　-再現率（Recall)≂TP/(TP+FN)

　　　-適合率(Precitsion)≂TP/（TP+FP)

　　　-F値…PrecisionとRecallの調和平均でRecallとPrecisionのバランスを示し、高ければ高いほどRecallとPrecisionがともに高くなる。

<br>

### ハンズオン

　　●設定<br>　　　○タイタニックの乗客データを利用しロジスティック回帰モデルを作成<br>　　　○特徴量抽出をしてみる<br>　　●課題<br>　　　○年齢が30歳で男の乗客は生き残れるか？

　　＜回答＞

　　下図の通り、30歳における生存確率は0.382（38.2％）。<br>
　　生存確率50％以下を脂肪と判定するのであれば、30歳の人は生存できない。

![alt](https://user-images.githubusercontent.com/77253188/104451398-d3d83b00-55e4-11eb-87b1-4b619b2aebc0.png)


<br><br><br>

## 機械学習　第4章 主成分分析
### 講義内容の要点

　　・主成分分析の意味

　　　-多数の説明変数から、目的変数の説明力が高いものを抽出する。

　　　-分散の大きい説明変数ほど説明力が高い。

　　・分析方法

　　　-説明変数間の分散共分散行列を算出。

　　　-固有値、固有ベクトルを算出　（対象行列なので、固有値はゼロ以上で、固有ベクトル同士は直行）

　　　-寄与率…上記固有値の全合計に対する個々の固有値の割合。

　　　-累積寄与率…上記固有値の全合計に対する第一主成分の分散から第k番目までの固有値合計の割合。

<br>

### ハンズオン

　　●設定<br>　　　○乳がん検査データを利用しロジスティック回帰モデルを作成<br>　　　○主成分を利用し2次元空間上に次元圧縮<br>　　●課題<br>　　　○32次元のデータを2次元上に次元圧縮した際に、うまく判別できるかを確認

　　＜回答＞


![alt](https://user-images.githubusercontent.com/77253188/104687515-b0c39d80-5742-11eb-80be-ef630ed89a2c.png)


<br>

## 機械学習　第5章 アルゴリズム
### 講義内容の要点

　　・k近傍法

　　　距離が近いk個のデータのうち、数が最も多いデータのクラスに分類する。

　　・k-means

　　　-教師なし学習

　　　-k個のデータに分類（設定したｋ個のクラスタ中心のうち、最も近いクラスタ中心を見つける）

![alt](https://user-images.githubusercontent.com/77253188/104689711-59273100-5746-11eb-8a43-0c35aeaf9b29.png)


<br>

### ハンズオン（kNN）

　　●ハンズオン設定<br>　　　○人口データを分類<br>　　　○配布済みのjupyter notebookを利用<br>　　●課題<br>　　　○人口データと分類結果をプロットしてください

　　＜回答＞

![alt](https://user-images.githubusercontent.com/77253188/104689402-cc7c7300-5745-11eb-93eb-894616394461.png)

<br><br><br>

## 機械学習　第7章 サポートベクターマシン（SVM)
### 講義内容の要点

　　・2クラス分類の手法（ロジスティック回帰と同類）

　　・線形判別関数　　y=w(T)x+b　(T)は転置

　　・線形判別関数とデータ点の距離（マージン）を最小化

　　・目的関数　min[1/2×||w||^2] 、制約条件　ti（w(T)xi+b）≧1　　→ラグランジュ未定乗数法にて解（w）を算出


![alt](https://user-images.githubusercontent.com/77253188/104690416-bec7ed00-5747-11eb-97a3-74ca47d85b55.png)


