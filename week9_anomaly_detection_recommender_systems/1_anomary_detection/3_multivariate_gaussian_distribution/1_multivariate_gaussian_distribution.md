## 多変量ガウス分布

### 動機付けの例: データセンターマシンモニタリングの場合

<img width="961" alt="2016-10-25 17 50 09" src="https://cloud.githubusercontent.com/assets/6447085/19679096/84b9ee74-9adb-11e6-845b-440a369cc473.png">

今までの異常検出アルゴリズムでは、データによっては上手く異常として検出できない場合がある。

### 多変量ガウス(正規)分布

<img width="962" alt="2016-10-25 17 51 20" src="https://cloud.githubusercontent.com/assets/6447085/19679132/a9b7b602-9adb-11e6-9819-8099ef9d29cc.png">

n次元のフィーチャーベクトルxに対してフィーチャー個別のモデリングではなく、全て一つにしたモデルを使う。 $\Sigma$ は和ではなく共分散行列。

### 多変量ガウス分布例

<img width="961" alt="2016-10-25 17 52 36" src="https://cloud.githubusercontent.com/assets/6447085/19679194/dd0251f2-9adb-11e6-9cb2-fb17f4ad16e2.png">

$\Sigma$ の値を減らすと山が高く鋭くなり、増やすと低く緩やかになる。

<img width="962" alt="2016-10-25 17 53 15" src="https://cloud.githubusercontent.com/assets/6447085/19679231/008b0d8a-9adc-11e6-8d86-31dea42e9c12.png">

また、 $\Sigma$ こ片方の値のみを小さくするとそれに対応したフィーチャーの分散が小さくなり、大きくすればフィーチャーの分散も大きくなる。

<img width="965" alt="2016-10-25 17 54 27" src="https://cloud.githubusercontent.com/assets/6447085/19679260/19cdb478-9adc-11e6-802a-cb2a66946cc0.png">

<img width="963" alt="2016-10-25 17 56 52" src="https://cloud.githubusercontent.com/assets/6447085/19679365/6f45f212-9adc-11e6-8397-b7d19f7bd0b9.png">

また、 $\Sigma$ の非対角成分の値を変えることによりフィーチャー同士の相関による分布をモデル化することもできる。負の値にすればフィーチャー同士の負の相関をモデル化することもできる。

<img width="963" alt="2016-10-25 17 57 29" src="https://cloud.githubusercontent.com/assets/6447085/19679397/894148ba-9adc-11e6-9445-5fc10e563431.png">

一方で、$\mu$ の値を変えることで分布の中心を移動できる。
