# 正規方程式(Normal equation)

<img width="760" alt="2016-07-04 19 08 40" src="https://cloud.githubusercontent.com/assets/6447085/16557439/c24b2ad8-421a-11e6-8028-b2bf7c4f817f.png">

正規方程式は $\theta$の値を解析的に解く方法です。最急降下法が何度もイテレーションを回す代わりに、正規方程式では基本的に1ステップで $\theta$ の値を求めることができます。

<img width="764" alt="2016-07-04 19 17 17" src="https://cloud.githubusercontent.com/assets/6447085/16557628/f5edd6f0-421b-11e6-9f86-5a7e098b7276.png">

コスト関数 $J(\theta)$ の値を最小にする $\theta$ の値を求めるためには、上記 $J_\theta$ の各パラメータ $\theta_j$ に関する偏微分 $\frac{\delta}{\delta\theta_j}J(\theta)$ をとり、これが0となる $\theta_0,\theta_1,...\theta_n$ の値を求めることでコスト関数 $J(\theta)$ を最小にする $\theta$ (右上グラフの青い点)を求めることができます。正規方程式はこれを行います。

<img width="762" alt="2016-07-04 19 32 09" src="https://cloud.githubusercontent.com/assets/6447085/16558025/0b90f9cc-421e-11e6-8f9d-4e86d690c9ee.png">

上記のようにデータセットのすべてのフィーチャーをX、答えをyにそれぞれまとめると

$$
X = \begin{bmatrix}
1 & 2104 & 5 & 1 & 45 \\
1 & 1416 & 3 & 2 & 40 \\
1 & 1534 & 3 & 2 & 30 \\
1 & 852 & 2 & 1 & 36
\end{bmatrix}

y = \begin{bmatrix}
460 \\
232 \\
315 \\
178
\end{bmatrix}
$$

$X$ は $m×(n+1)$ 次元行列、$y$ は $m$ 次ベクトルになります。（ $m$ はデータセットの数、$n$ 、はフィーチャーの数です。また、 $x_0$ は1と慣習的に置きます）

そして次の式を解くことで $\theta$ の値を求めることができます。
$$
\theta = (X^TX)^{-1}X^Ty
$$
これが正規方程式のおおまかな手順です。

<img width="760" alt="2016-07-04 21 08 05" src="https://cloud.githubusercontent.com/assets/6447085/16559974/7c137104-422b-11e6-80cc-d3dff4220f8c.png">


正規方程式 $\theta = (X^TX)^{-1}X^Ty$ に関してそれぞれの行列を構築・計算するための抽象化の手順を見ていきます。

$X$ はデザイン行列とも呼ばれており、これの構築方法は以下になります。

$m$ 個のトレーニングセット、$n$ 個のフィーチャーがあるとして、$x^{(i)}$ は$n+1$次元のフィーチャーベクトルになります。
$$
x^{(i)} = \begin{bmatrix}
x^{(i)}_0 \\
x^{(i)}_1 \\
x^{(i)}_2 \\
\vdots \\
x^{(i)}_n
\end{bmatrix}
\in\mathbb{R}^{n+1}
$$
上記のフィーチャーベクトルの転置行列を上から順に並べるとデザイン行列$X$になります。
$$
X = \begin{bmatrix}
(x^{(1)})^T \\
(x^{(2)})^T \\
(x^{(3)})^T \\
\vdots \\
(x^{(m)})^T
\end{bmatrix}
= \begin{bmatrix}
x^{(1)}_0 & x^{(1)}_1 & x^{(1)}_2 & \cdots & x^{(1)}_n \\
x^{(2)}_0 & x^{(2)}_1 & x^{(2)}_2 & \cdots & x^{(2)}_n \\
x^{(3)}_0 & x^{(3)}_1 & x^{(3)}_2 & \cdots & x^{(3)}_n \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
x^{(m)}_0 & x^{(m)}_1 & x^{(m)}_2 & \cdots & x^{(m)}_n
\end{bmatrix}
= \begin{bmatrix}
1 & x^{(1)}_1 & x^{(1)}_2 & \cdots & x^{(1)}_n \\
1 & x^{(2)}_1 & x^{(2)}_2 & \cdots & x^{(2)}_n \\
1 & x^{(3)}_1 & x^{(3)}_2 & \cdots & x^{(3)}_n \\
\vdots & \vdots & \vdots & \vdots & \vdots \\
1 & x^{(m)}_1 & x^{(m)}_2 & \cdots & x^{(m)}_n
\end{bmatrix}
$$

<img width="761" alt="2016-07-04 21 51 11" src="https://cloud.githubusercontent.com/assets/6447085/16560957/76d3bf72-4231-11e6-84c7-864bfed1fce8.png">

$\theta = (X^TX)^{-1}X^T$y において $(X^TX)^{-1}$ とは $X^TX$ の逆行列です。

Octaveでは pinv(X'*X)*X'*y というふうなコードになります。

また正規方程式を使う際はフィーチャーのスケーリングは必要ありません。

<img width="761" alt="2016-07-04 22 04 14" src="https://cloud.githubusercontent.com/assets/6447085/16561279/47fdc9c0-4233-11e6-9bdc-067c6fda0cd0.png">


### 最急降下法と正規方程式のメリット・デメリット

#### 最急降下法
- 学習率αを選ぶ必要がある
- 何度もイテレーションを回す必要がある
- フィーチャーの数が多い場合でも問題なく早く収束する

#### 正規方程式
- 学習率αを選ぶ必要はない
- 1回のステップで完了する
- $(X^TX)^{-1}$ を計算する必要がある($n×n$行列の計算コストは大体 $O(n^3)$ のオーダー)
- 上記のためフィーチャー数が多い場合非常に遅くなる
- $n = 1000$ 程度までなら正規方程式は十分早いが、$n = 10000$ くらいになると速度が低下し始め、 $n = 10^6$ では最急降下法のほうが早くなる
- $n = 10000$ 辺りから最急降下法を適用することを検討する

フィーチャー数nが小さい場合(1000程度)は正規方程式、大きい場合(10000以上)は最急降下法を使うのがベターです。
