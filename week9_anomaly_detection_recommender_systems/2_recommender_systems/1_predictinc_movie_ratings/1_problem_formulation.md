# レコメンドシステム

## 問題の定式化

### 映画のレーティングの例

<img width="964" alt="2016-10-25 18 05 22" src="https://cloud.githubusercontent.com/assets/6447085/19679677/a0725366-9add-11e6-8064-d5ac7ee778f9.png">

各人が各映画を星の数でレーティングする。 $n_u$ がユーザー数、 $n_m$ が映画の数、 $r(i, j)$ がj番目のユーザーがi番目の映画をレーティングしているかどうか、 $y^{(i, j)}$ がj番目のユーザーがi番目のユーザーにつけたレーティングの値( $r(i, j)$ が1のもののみ)。レコメンドシステムはこれらのレーティングのうち欠けた部分を埋め合わせることを目的とする。