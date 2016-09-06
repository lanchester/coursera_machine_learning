## 主成分分析問題の定式化

PCA(principal component analysis) はDimensionaly reduction で最も人気のあるアルゴリズム。

### PCAの定式化

<img width="967" alt="2016-09-06 14 48 34" src="https://cloud.githubusercontent.com/assets/6447085/18262938/06622d90-7441-11e6-922d-f19866bb52ad.png">

2次元のフィーチャーを1次元に削減するために、フィーチャーベクトルを射影するための直線を、二乗和の距離が最も短くなるようにして求めたい。ちなみにPCAを適用する前にはフィーチャースケーリング(平均標準化)をしておく。

### PCAの定式化

<img width="960" alt="2016-09-06 14 49 12" src="https://cloud.githubusercontent.com/assets/6447085/18262950/1dfade02-7441-11e6-9d1b-af3d1be19670.png">

一般的に、PCAではn次元ベクトルのフィーチャーをk次元ベクトルに減らすために、各フィーチャーを射影するk個のベクトルを求める。

### PCAは線形回帰ではない

<img width="962" alt="2016-09-06 14 50 01" src="https://cloud.githubusercontent.com/assets/6447085/18262957/3665d974-7441-11e6-94ad-af56095d698a.png">

左の線形回帰では誤差はyの値と比べたときのものなので実際のyとの距離を言う。右のPCAでは射影する直線に対して最短距離をとるため垂線を引き誤差とする。これはデータセットによっては全く違う結果を示す。また、線形回帰ではのそくするためのyが必要だが、PCAには必要ない。また、PCAではどのデータも同様に扱われる。
