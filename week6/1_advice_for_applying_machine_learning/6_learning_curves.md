## 学習曲線

正当性やパフォーマンス、バイアス／バリアンス問題がないかチェックするのに有用。

### 学習曲線

![2016-08-01 15 47 05](https://cloud.githubusercontent.com/assets/6447085/17285685/38cc8bda-57ff-11e6-8cde-028ee5ce8571.png)

$J_{train}(\theta)$ か $J_{cv}(\theta)$ をトレーニング手本の数 $m$ の関数としてプロットする。通常 $m$ は例えば100などの定数だが人工的に10,20,30などに減らしその時の誤差をプロットする。

$J_{train}(\theta)$ の場合トレーニングセットが少なければ誤差は小さくなり、例えばモデルの次数が2なら $m=3$ までは正規化項が無ければ誤差は0になる。逆に $m$ が大きくなれば誤差は増える。$J_{cv}(\theta)$ の場合、 $m$ を増やすほど一般化できるため誤差は減少する。

### 高バイアス

![2016-08-01 15 47 56](https://cloud.githubusercontent.com/assets/6447085/17285703/57bac35e-57ff-11e6-9616-4f68fc8d0efc.png)

高バイアスの場合、 $J_{cv}(\theta)$ は $m$ が小さいと誤差は極端に大きく $m$ を増やすとすぐに平坦になる。 $J_{train}(\theta)$ は最初は小さいがすぐに大きくなり、その値は $J_{cv}(\theta)$ とほぼ同じになり、その値は高いものとなる。

高バイアスの場合 $m$ を増やしても $J_{cv}(\theta)$ は小さくならない。つまり、トレーニングデータを集めても無駄ということが事前に分かる。

### 高バリアンス

![2016-08-01 15 48 31](https://cloud.githubusercontent.com/assets/6447085/17285709/6c6ccc70-57ff-11e6-9852-70b2c0e802f4.png)

100次の多項式の仮説を例とすると、 $J_{train}(\theta)$ は $m$ が小さければデータに完全にフィットし、$m$ を増やしても誤差はそれほど大きくならない。

逆に $J_{cv}(\theta)$ の値は高いままあまり下がらない。つまり高バリアンス時の診断のポイントは $J_{cv}(\theta)$ と $J_{cv}(\theta)$ の間に大きな差がある。そしてこの場合には、データセットを増やしていくと誤差は収束していく
