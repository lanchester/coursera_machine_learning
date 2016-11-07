# 異常検出

## 問題の動機

### 異常検出の例

<img width="963" alt="2016-10-25 17 26 40" src="https://cloud.githubusercontent.com/assets/6447085/19678329/44b5f302-9ad8-11e6-9936-177034f90fd3.png">

航空機のエンジンに異常がないか知りたい時、熱や振動などのデータをフィーチャーとして今までのデータから大きく外れていれば異常と見なして再テストを行う。

### 密度推定

<img width="961" alt="2016-10-25 17 27 54" src="https://cloud.githubusercontent.com/assets/6447085/19678354/6385fb74-9ad8-11e6-8d74-279ebe1ada5d.png">

与えられたフィーチャーxに対しモデルP(x)を構築してその値がある値 $\epsilon$ より大きければOK、小さければ異常と見なす。

### 異常検出の例

<img width="964" alt="2016-10-25 17 28 27" src="https://cloud.githubusercontent.com/assets/6447085/19678378/7949858e-9ad8-11e6-86e0-ec9d56714957.png">

webサイト上での詐欺の検出、製造業、データセンターのマシンの異常検出等
