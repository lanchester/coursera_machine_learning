## アルゴリズム

### 密度推定

<img width="961" alt="2016-10-25 17 32 19" src="https://cloud.githubusercontent.com/assets/6447085/19678521/0d02d5aa-9ad9-11e6-8930-158085156be8.png">

$x_1$から$x_n$までのトレーニングセットについて正規分布のモデルは $p(x_n; \mu_n; \sigma_n^2)$ を掛け合わせたものになる。

### 異常検出アルゴリズム

<img width="963" alt="2016-10-25 17 33 27" src="https://cloud.githubusercontent.com/assets/6447085/19678551/2ef23994-9ad9-11e6-9e9a-9935da46ec82.png">

1. 異常と見なせる手本を探す。(あるいは正常な手本を集める)
2. 1のラベルなし手本に対して $\mu_j, \sigma_j^2$ を求める。(jはフィーチャーベクトルの各要素)
3. 新しいデータに対しモデルp(ガウス分布確率)を求め、ある値 $\epsilon$ より小さければ異常と見なす

### 異常検出例

<img width="963" alt="2016-10-25 17 34 10" src="https://cloud.githubusercontent.com/assets/6447085/19678568/447b8f7c-9ad9-11e6-963f-5e2ae7039d61.png">

左上のグラフにおいて $x_1$ の平均 $\mu_1$ は約5、標準偏差 $\sigma_1^2$ は約2、$x_2$ の平均 $\mu_2$ は約3、標準偏差 $\sigma_2^2$ は約1とする。ここで新しい点が与えられた場合、左下の3次元グラフにおいてその点をプロットしたときの高さが $p(x)$ になる。この $p(x)$ が $\epsilon$ より小さいものを全て異常とする。
