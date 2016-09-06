# 教師なし学習: 次元削減

## 動機1: データ圧縮

### データ圧縮

<img width="964" alt="2016-09-06 14 31 52" src="https://cloud.githubusercontent.com/assets/6447085/18262676/d01a2e2e-743e-11e6-9f8a-78307f0c0c40.png">

<img width="963" alt="2016-09-06 14 33 22" src="https://cloud.githubusercontent.com/assets/6447085/18262688/e259123a-743e-11e6-9635-cf9ca5f2e491.png">

センチとインチで単位が違うだけで同じ長さのフィーチャーを一つにしたい、あるいはパイロットの能力と楽しみ具合のように高い相関のあるフィーチャーのベクトルは直線的な相関関係にあり、それをある直線に射影するとそれらのデータこ近似を一つの値のみで表せるようになる。

<img width="965" alt="2016-09-06 14 34 16" src="https://cloud.githubusercontent.com/assets/6447085/18262703/02b3df06-743f-11e6-84f3-7399d062abe8.png">

<img width="962" alt="2016-09-06 14 34 54" src="https://cloud.githubusercontent.com/assets/6447085/18262719/1b9de322-743f-11e6-8c7c-0f40df23f431.png">

3次元ベクトルの場合も3次元データを2次元平面に射影することで2次元ベクトルに圧縮することができる。
