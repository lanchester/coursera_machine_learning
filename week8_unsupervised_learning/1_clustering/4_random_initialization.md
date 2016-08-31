## ランダム初期化

### k平均法

<img width="962" alt="2016-08-31 12 28 58" src="https://cloud.githubusercontent.com/assets/6447085/18114995/aceebd2e-6f76-11e6-8b17-b2edb1d75322.png">

ランダム初期化には良い方法がある。

### ランダム初期化

<img width="962" alt="2016-08-31 12 30 45" src="https://cloud.githubusercontent.com/assets/6447085/18115006/c435707c-6f76-11e6-85dc-92fac7ddd4b9.png">

まずクラスタ数Kは手本数mより小さい値を決める。次にK個の手本をランダムに選び、それを $\mu_1 ~ \mu_K$ にセットする。

### 局所最適

<img width="962" alt="2016-08-31 12 31 23" src="https://cloud.githubusercontent.com/assets/6447085/18115015/da0a663c-6f76-11e6-9c69-61ea209da215.png">

k平均法では初期値によって局所最適に陥ることがある。そのためランダム初期化は複数試してみるのが良い。

### ランダム初期化

<img width="963" alt="2016-08-31 12 31 58" src="https://cloud.githubusercontent.com/assets/6447085/18115026/ef011de2-6f76-11e6-9870-a316a21a6239.png">

具体的にはランダム初期化ステップを含めたk平均法を100回ほど行い、その中で最も最適化されたコスト関数のクラスタリングを採用する。クラスタ数が10程度までであれば複数回のランダム初期化は良い結果になる。クラスタ数が数百の場合は最初の1回ですでに良い結果になっていることが多い。
