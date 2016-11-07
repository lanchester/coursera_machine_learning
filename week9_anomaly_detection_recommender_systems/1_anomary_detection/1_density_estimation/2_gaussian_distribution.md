## ガウス分布

### 正規分布

<img width="961" alt="2016-10-25 17 29 33" src="https://cloud.githubusercontent.com/assets/6447085/19678414/a3ccdc02-9ad8-11e6-80e9-3afa2223efb3.png">

$\mu$ を平均、 $\sigma^2$ を分散として正規分布の式を表す。 $\mu$ が中心で $\sigma$ が分布の範囲になる。 $\sim$ は分布の意味。

### ガウス分布の例

<img width="964" alt="2016-10-25 17 30 25" src="https://cloud.githubusercontent.com/assets/6447085/19678451/c6242d96-9ad8-11e6-80b2-9b4956455310.png">

$\sigma$ が小さいと山の背が高く鋭くなり、大きいと低く緩やかになる。山の面積は積分すると1になる。(確率分布の性質による)

### パラメータ推計

<img width="964" alt="2016-10-25 17 31 22" src="https://cloud.githubusercontent.com/assets/6447085/19678471/e0557d00-9ad8-11e6-8d88-c6916655b34b.png">

フィーチャーXの分布を正規分布で表す。データセットがどこを中心として標準偏差がどの程度あるか $\mu, \sigma^2$ の値が何になるかを求める。

$\mu$ は各手本の平均、 $\sigma^2$ は手本から平均を引いた値になる。このパラメータを推定する方法は最尤推定と呼ばれる。
