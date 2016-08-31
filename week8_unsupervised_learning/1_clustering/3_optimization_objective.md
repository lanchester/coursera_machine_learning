## 最適化の目的

### k平均法最適化の目的

<img width="962" alt="2016-08-31 11 28 53" src="https://cloud.githubusercontent.com/assets/6447085/18113906/2a361d58-6f6e-11e6-8c75-369d415d1e1d.png">

$C^{(i)}$ は $x^{(i)}$ がどのクラスタに割り当てられているかのインデックスを管理する変数、 $\mu_k$ はクラスタ重心、 $\mu_{c^{(i)}}$ はサンプル $x^{(i)}$ が割り当てられたクラスタ重心。これらの変数を使ってコスト関数を最適化していく。k平均法のコスト関数はディストーションコスト関数とも呼ばれる。

### k平均法

<img width="962" alt="2016-08-31 11 29 48" src="https://cloud.githubusercontent.com/assets/6447085/18113933/40f79a44-6f6e-11e6-9dc2-47aa528316f1.png">

まずk個のクラスタ重心をランダムに初期化し、2つのステップを繰り返す。クラスタ割り付けステップでは1からmまでの手本について各クラスタ重心との距離のコスト関数を最小化するクラスタ重心を求める。次に重心移動ステップでコスト関数を位置の観点から最小化する $\mu$ を選ぶ。