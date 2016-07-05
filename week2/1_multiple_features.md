# week2: 線形回帰 - 多変量線形回帰1
## 複数フィーチャーの場合
<img width="719" alt="2016-07-02 4 35 02" src="https://cloud.githubusercontent.com/assets/6447085/16542181/a829b936-40d9-11e6-91df-3f7171417dee.png">


フィーチャーが複数ある場合、仮説の係数を $\theta_0, \theta_1, ...$ と表記する代わりにベクトル形式でまとめて表記します。
$$
\theta = \left[
    \begin{array}{rrr}
      \theta_0 \\
      \theta_1 \\
      \theta_2 \\
      \theta_3
    \end{array}
  \right]
\
$$

$m$ => データ量

$n$ => フィーチャー数

$x$ => $n$次元ベクトル <= $\mathbb{R}^n$ ($\mathbb{R}$ は実数の集合)

$x^{(i)}$ => 表のi行目

例
$$
x^{(2)} = \left[
    \begin{array}{rrr}
      1416 \\
      3 \\
      2 \\
      40
    \end{array}
  \right]
\
$$

$x^{(i)}_j$ => i行j列目のフィーチャー ($x^{(2)}_3 = 2$)

<img width="719" style="margin-bottom:10px;" alt="2016-07-02 4 35 02" src="https://cloud.githubusercontent.com/assets/6447085/16542194/19ae31f4-40da-11e6-9e21-f5bc6bf90ee4.png">

<img width="722" alt="2016-07-02 5 39 33" src="https://cloud.githubusercontent.com/assets/6447085/16542316/a5447120-40de-11e6-83fe-05c715125d35.png">

フィーチャーが複数の場合の仮説
$$
h_\theta(x) = \theta_0 + \theta_1x_1 + \theta_2x_2 + \theta_3x_3 + \theta_4x_4
$$
は一般的に
$$
h_\theta(x) = \theta_0 + \theta_1x_1 + \theta_2x_2 + ... + \theta_nx_n
$$
で表せます。
ここで慣習的に$ x_0 = 1 $と定義すると上の仮説は以下のように書くことができます。
$$
h_\theta(x) = \theta_0x_0 + \theta_1x_1 + \theta_2x_2 + ... + \theta_nx_n
$$
$$
h_\theta(x) = \theta^TX
$$
$\theta^T$ は $\theta$の転置行列です。つまりn+1行1列行列とn+1次元ベクトルとの内積として仮説をコンパクトに書き直したものになります。これは単純に仮説の数式を短く表したもので特別な操作をしているわけではありません。


#### おまけ
フィーチャーと係数はそれぞれ0~nまでのn+1次元ベクトルで表します。
$$
X = \left[
    \begin{array}{rrr}
      x_0 \\
      x_1 \\
      x_2 \\
      : \\
      x_n
    \end{array}
  \right]
\
$$

$$
\theta = \left[
    \begin{array}{rrr}
      \theta_0 \\
      \theta_2 \\
      : \\
      \theta_n
    \end{array}
  \right]
\
$$
$X$の転置行列は要素を上から順に並べていって
$$
X^T = \left[
    \begin{array}{rrr}
      x_0 &
      x_1 &
      x_2 &
      ... &
      x_n
    \end{array}
  \right]
\
$$
なので
$$
X^T\theta = \theta_0x_0 + \theta_1x_1 + \theta_2x_2 + ... + \theta_nx_n
$$
になります。内積の計算についてはググってみてください。
