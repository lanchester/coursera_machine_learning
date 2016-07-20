## マルチクラス分類

### 複数分類器

![2016-07-20 16 42 19](https://cloud.githubusercontent.com/assets/6447085/16978829/f4b7a408-4e98-11e6-9243-d4594eb2656a.png)

one-vs-all法の拡張で実現する。例えば4種類に分類したい場合出力レイヤに4つのユニットを設定し、各ユニットでは画像が歩行者かどうか、車かどうかの分類を行う。

この時の $h_\theta(x)$ は4次元ベクトルとなり、画像が歩行者なら
$$
\left[
\begin{array}{rrr}
1 \\
0 \\
0 \\
0
\end{array}
\right]
$$
のようになる。

### 複数分類器

![2016-07-20 16 43 02](https://cloud.githubusercontent.com/assets/6447085/16978844/105ec98e-4e99-11e6-9660-05d74edc6b8f.png)

つまりニューラルネットワークでn種類のマルチクラス分類をする場合はトレーニングセットのラベルには今までの整数の代わりに
$$
\left[
\begin{array}{rrr}
1 \\
0 \\
0 \\
0
\end{array}
\right]
$$
のようなn次元ベクトルを与える。
