## 最大マージン

### サポートベクターマシン

<img width="965" alt="2016-08-29 17 17 19" src="https://cloud.githubusercontent.com/assets/6447085/18045176/7c166da2-6e0c-11e6-80fc-ea42299be672.png">

SVMで陽性と判断する際には $\theta^Tx$ が0以上であれば良いがコスト関数にはギリギリの閾値ではなくある程度のセーフティマージンをとりたい。

### SVM決定境界

<img width="963" alt="2016-08-29 17 18 22" src="https://cloud.githubusercontent.com/assets/6447085/18045207/a061e36c-6e0c-11e6-9916-7b27c08fc8fc.png">

コスト関数の $C$ を非常に大きな値にした場合、最初の項は0になる。最初の項を0として、 $y^{(i)}=1$ なら $\theta^Tx^{(i)} \gg 1$、 $y=0$ なら $\t
heta^Tx^{(i)} \ll -1$ としたい。これを最適化して $\theta$ の値を決定する。

### SVM決定境界: 線形分離可能な場合

<img width="965" alt="2016-08-29 17 19 38" src="https://cloud.githubusercontent.com/assets/6447085/18045235/cd3c2078-6e0c-11e6-86fe-3ba35f240f9f.png">


決定境界は境界値ギリギリで分類するのではなく、陰性陽性それぞれから距離をなるべく大きくとるよう余裕を持った決定境界になる。

この距離をマージンと言い、SVMはこれが最も大きくなるよう堅牢性のある仮説を作る。

### 外れ値が存在する最大マージン分類器

<img width="963" alt="2016-08-29 17 20 36" src="https://cloud.githubusercontent.com/assets/6447085/18045258/f17e9ee8-6e0c-11e6-81c8-4c8d131a6498.png">

SVMはただ大きなマージンをとるだけでなく、手本から大きく外れた外れ値によって決定境界を変えずに最もそれらしい決定境界を選ぶことができる。その際は $C$ は大きすぎる値を入れない。
