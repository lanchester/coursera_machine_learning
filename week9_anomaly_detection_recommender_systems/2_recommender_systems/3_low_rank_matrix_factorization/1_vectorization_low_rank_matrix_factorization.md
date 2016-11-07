## 低ランク行列分解

### 協調フィルタリング

<img width="959" alt="2016-10-25 18 19 33" src="https://cloud.githubusercontent.com/assets/6447085/19680162/99bd8b88-9adf-11e6-980c-5568d14767ec.png">
レーティングを行列で表す。

### 協調フィルタリング

<img width="963" alt="2016-10-25 18 20 15" src="https://cloud.githubusercontent.com/assets/6447085/19680191/b5b3e0a8-9adf-11e6-9f3c-1bf99a6d43d4.png">

行列の各要素の値は $(\theta^{(n_u))^T(x^{(n_m)})}$ で予測される。この行列は $Xと\Theta$ の２つの行列で表される。Xは各映画のフィーチャーベクトルの転置ベクトルを列とした行列、 $\Theta$ はユーザー毎のパラメータベクトルの転置ベクトルを列とした行列。

この２つの行列に分けることを低ランク行列分解と言う。

### 関連した映画を見つける

<img width="962" alt="2016-10-25 18 21 22" src="https://cloud.githubusercontent.com/assets/6447085/19680225/db8dd7c0-9adf-11e6-9431-193ec8f83f04.png">
