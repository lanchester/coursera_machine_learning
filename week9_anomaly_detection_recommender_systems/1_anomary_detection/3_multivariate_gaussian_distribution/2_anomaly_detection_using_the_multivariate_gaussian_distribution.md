## 多変量ガウス分布を用いた異常検出

### 多変量ガウス(正規)分布

<img width="963" alt="2016-10-25 17 59 04" src="https://cloud.githubusercontent.com/assets/6447085/19679453/bd9aafd4-9adc-11e6-8f61-7ceb692f028c.png">

多変量ガウス分布を用いて異常検出アルゴリズムを走らせる場合、パラメータ $\mu, \Sigma$ はPCAの時と同じように $\mu$ には平均、 $\Sigma$ はその値を使った式を代入する。

### 多変量ガウス分布を用いた異常検出

<img width="962" alt="2016-10-25 17 59 49" src="https://cloud.githubusercontent.com/assets/6447085/19679476/d8e0c314-9adc-11e6-878e-4ad09d84cb2a.png">

異常検出に多変量ガウス分布を使う時は
1. モデル $p(x)$ を決めるため $\mu, \Sigma$ を求める
2. 新しいデータに対して $p(x)$ の値を求める
2の結果が $\epsilon$ より小さければ異常と見なす

### オリジナルモデルとの関係性

<img width="962" alt="2016-10-25 18 00 24" src="https://cloud.githubusercontent.com/assets/6447085/19679503/f81e3b44-9adc-11e6-9746-4bf6aa748d26.png">

<img width="960" alt="2016-10-25 18 01 04" src="https://cloud.githubusercontent.com/assets/6447085/19679540/1138fcae-9add-11e6-9295-e5c0b260bef3.png">

元の正規分布によるモデルは多変量ガウス分布の軸を固定した場合のものとして見なすことができる。つまり共分散行列の非対角要素を全て0とした場合と同等。

### オリジナルモデルvs多変量ガウス分布モデル

<img width="961" alt="2016-10-25 18 02 10" src="https://cloud.githubusercontent.com/assets/6447085/19679566/324c6d4a-9add-11e6-9587-6196b6e8adc8.png">

普通はオリジナルモデルの方を使うことが多い。多変量ガウス分布モデルではフィーチャー同士の相関を捉えることができるが、オリジナルモデルでも相関した値をフィーチャーとして加えれば同様のことができる。また、フィーチャー数nが大きい時、多変量ガウス分布モデルは共分散行列の計算に時間がかかり、オリジナルモデルと比べて遅くなる。また、データセット数mが小さい場合でもオリジナルモデルは上手く機能するが、多変量ガウス分布モデルはそもそも適用できない。大体 $m > 10n$ なら良く機能する。最後に、稀なケースだが、多変量ガウス分布の実装では $m > n$ と冗長なフィーチャー(線形従属)がないかに気を付ける必要がある。