## スキュー(歪んだ)したクラスのエラーメトリクス

エラーメトリクスとは直前の単一実数の評価指標のこと。

### ガン分類例

<img width="967" alt="2016-08-08 14 13 34" src="https://cloud.githubusercontent.com/assets/6447085/17469867/5409839e-5d72-11e6-9012-4c5affcb9d93.png">

あるガン分類器のテストセットでの誤差が1%であっても、実際にガンであったのは全体の0.5%であった場合、1%の誤差は高い精度とは言えない。ただ0を出力するだけの関数ですら誤差は0.5%になってしまうためである。

このように陽性と陰性の割合が両極端になる場合スキュードクラスと言う。スキュードクラスではエラーメトリクスには誤差ではなく別の指標が必要になる。

### 精度と再現率

<img width="962" alt="2016-08-08 14 14 14" src="https://cloud.githubusercontent.com/assets/6447085/17469883/69600588-5d72-11e6-9127-a44b85d1da29.png">

予測と結果と実際の結果の組み合わせによって4つのケースにわけた場合、それぞれtrue positive(真陽性)、false positive(偽陽性)、false negative(偽陰性)、false negative(偽陰性)にわけられる。

この時presicion(精度)は $\frac{true pos}{predicted pos(予測の陽性数)} = \frac{true pos}{true pos + false pos}$ となる。
またrecall(再現率)は $\frac{true pos}{actual pos(実際の陽性数)} = \frac{true pos}{true pos + false neg}$ となる。

ガン分類器の例なら常に0を出力する予測は再現率が0となるので良い分類器とは言えないことがわかる。一般的に精度も再現率も高い分類は良いものである。
