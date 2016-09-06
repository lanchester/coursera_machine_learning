## 主成分分析アルゴリズム

### データ処理

<img width="963" alt="2016-09-06 14 51 23" src="https://cloud.githubusercontent.com/assets/6447085/18262990/6be1b870-7441-11e6-9deb-2a5ffa22f3c9.png">

PCAを使う前には必ずデータの各フィーチャーをフィーチャーの平均で引く、平均標準化をしなければならない。データのスケールが違いすぎる場合はフィーチャースケーリングも必要になる。フィーチャースケーリングはフィーチャーの値から平均値を引いて標準偏差で割る手法が一般的。標準偏差の代わりに最大値から最小値を引いた値でも良い。

### PCAアルゴリズム

<img width="962" alt="2016-09-06 14 52 09" src="https://cloud.githubusercontent.com/assets/6447085/18263015/8da86b16-7441-11e6-8ae5-32e341e2ff5d.png">

PCAはより低い次元のベクトルに射影したときの距離の誤差が最も小さくなるようなベクトル $u$ を探す。

左は2次元ベクトルを1次元ベクトルに射影し、 $x^{(1)}, x^{(2)}, x^{(3)}, ... $ を $z^{(1)}, z^{(2)}, z^{(3)}, ... $ に変換する。PCAは射影ベクトル $u$ とこれらの $z^{(1)}, z^{(2)}, z^{(3)}, ... $ ベクトルの2種類を計算する。

### PCAアルゴリズム

<img width="962" alt="2016-09-06 14 53 11" src="https://cloud.githubusercontent.com/assets/6447085/18263032/afe9ed58-7441-11e6-8c6d-d3ff5533a2a4.png">

手順
1. 共分散行列 $\Sigma$ を求める
2. $\Sigma$ の固有ベクトルを求める
$\Sigma$ はn×n行列でsvd(特異値分解)によって $[u, s, v] = svd(\Sigma)$ の3つの行列が得られる。このうちのuのみを使う。uもn×n行列になる。

### PCAアルゴリズム

<img width="963" alt="2016-09-06 14 54 11" src="https://cloud.githubusercontent.com/assets/6447085/18263050/cf0182e6-7441-11e6-8744-13209b10301c.png">

n×n行列のUから最初のk列を取りだしてn×k行列を作り $U_{reduce}$ とする。n次元ベクトルのフィーチャーxをk次元ベクトルのフィーチャーzに置き換えたい時、
$U_{reduce}^Tx$ を計算することががzを求めるための方法になる。

### PCAアルゴリズムまとめ

<img width="961" alt="2016-09-06 14 54 46" src="https://cloud.githubusercontent.com/assets/6447085/18263056/e3201224-7441-11e6-8eba-e801d914cc5f.png">

以上をまとめると、まずフィーチャーを平均標準化し、その平均を0にした上で、必要ならフィーチャースケーリングを行う。次に共分散行列 $\Sigma$ を求める。(この時、もしトレーニングセットが行として与えられている行列が存在する場合はより計算量の少ない方法がある)。次にsvdルーチンを使って[u, s, v]のうちU行列を求め、そのk列目までの $U_,{reduce}$ 行列の転地行列にxを掛けると、次元が削減されたzベクトルが求められる。