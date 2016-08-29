# サポートベクターマシン

## 最適化の目的

アルゴリズムのパフォーマンスはどれも似ていて、どのアルゴリズムを使うかと言うことは重要でないことが多い。それよりもデータ量やフィーチャーの選択、正規化パラメータの選び方といった機械学習のためのスキルのほうが重要なことが多い。しかしそれでもSVMに関しては複雑な非線形関数を予測するのに有用である。

### 分類の代替案

<img width="959" alt="2016-08-29 17 10 21" src="https://cloud.githubusercontent.com/assets/6447085/18045036/bcb4cf8a-6e0b-11e6-8b25-73ca3eac0d90.png">

分類のシグモイド関数を復習しSVMへの考え方を辿る。 $y=1$ なら $h_{\theta}(x) \approx 1, \theta^T x\gg 0$ を出力したい。 $y=0$なら $h_{\theta}(x) \approx 0, \theta^T x\ll 0$ したい。

### 分類の代替案

<img width="968" alt="2016-08-29 17 12 50" src="https://cloud.githubusercontent.com/assets/6447085/18045057/dc8ab3c4-6e0b-11e6-97ee-c932587e1453.png">

分類のコスト関数はスライドのようになり、 $y=1$ の時は $z \gg 0$ と予測したいのでzの値が大きくなるほど誤差の値は小さくなる。これが分類で用いたコスト関数だった。

このコスト関数を少し変更して $z=1$ で2つの直線に分ける。そして $Cost_1(z)$ とする。

$y=0$ の場合も同様に $z=-1$ で2つの直線に分けて $Cost_0(z)$ とする。ここからSVMを構築する。

### サポートベクターマシン

<img width="967" alt="2016-08-29 17 14 02" src="https://cloud.githubusercontent.com/assets/6447085/18045092/078500a2-6e0c-11e6-8f2b-841cc33c538b.png">

分類のコスト関数のうち $-log h_\theta (x^{(i)})$ を $Cost_1(z)$ 、 $(-log(1-h_\theta(x^{(i)}) ))$ を $Cost_0(z)$ を使ってを置き換える。 $\frac{1}{m}$ もコスト関数としてはただの定数なので無視する。

また正規化項のパラメータに $\lambda $ で重み付けをする代わりに、前半の項に $C$ をかける。 $C = \frac{1}{\lambda}$ である。
$$
min{}{\theta}C\sum{i=1}{m}[y^{(i)} cost_1(\theta^Tx^{(i)}) + (1 - y^{(i)})\cos t_0 (\theta^T x^{(i)})] + \frac{1}{2}\sum_{i=1}{n}\theta_j^2
$$

### SVMの仮説

<img width="963" alt="2016-08-29 17 14 53" src="https://cloud.githubusercontent.com/assets/6447085/18045119/28aa1e3e-6e0c-11e6-9f60-d9047a3c1d09.png">

SVMは確率ではなく直接1か0を出力する。つまり仮説は $\theta^T x \gg 0$ の時 $h_{\theta (x)} = 1$ 、それ以外を $h_{\theta (x)} = 0$ と出力する。
