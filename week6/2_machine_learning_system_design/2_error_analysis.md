## エラー分析

### おすすめのアプローチ

<img width="962" alt="2016-08-08 12 22 35" src="https://cloud.githubusercontent.com/assets/6447085/17468421/d3bda33c-5d62-11e6-87b9-65aa11f2e8e8.png">

- シンプルなアルゴリズムで素早く実装し、クロスバリデーションセットでテストする
- 学習曲線をプロットし、データが必要なのか、フィーチャーが必要なのかなどを診断する
- エラー分析: クロスバリデーションセットで誤分類された例を人力で見て分析する

### エラー分析

<img width="966" alt="2016-08-08 14 08 20" src="https://cloud.githubusercontent.com/assets/6447085/17469789/998cd034-5d71-11e6-8979-c17025e10787.png">

500件のクロスバリデーションセットのうち100件誤分類していた場合、この100件を手動で見て、メールの種類によって分類する(薬の販売、偽の商品の販売、フィッシングなど)。

この時にフィッシングスパムに対して効果が薄い等がわかれば、それに関するフィーチャーを加える、開発することに時間を割くことができる。

エラー分析によって予測の精度をあげて、分類が困難な例とはどんなものかを見つけ出すことができる。こういった例はアルゴリズムを変えても同様に困難なことが多い。

### 数値的評価の重要性

<img width="961" alt="2016-08-08 14 10 26" src="https://cloud.githubusercontent.com/assets/6447085/17469823/e156339c-5d71-11e6-9b74-f002bec03998.png">

学習アルゴリズムを評価する際にエラーでも正確さでも単一の実数のみを返す方法を確保しておくと役に立つ。

類似単語の検出には例えば先頭の数文字を見るなどがある(Porter stemmer などが有名)。しかしこれはuniverseとuniversityを同一と見なすこともあるため常にいれたほうが良いとは限らない。

これを判断するにはエラー分析は役に立たず実際に試すしかない。そこで実数のみを返すアルゴリズムの評価方法を使って、ソフトウェアありとなしの場合のクロスバリデーション誤差を見て、その評価の良し悪しを簡単に比べることでどちらが良いか判断できる。

このような評価方法はステミングの例の他にも大文字小文字の同一視をするべきかどうかなどの判断も素早く行うことができる。

その他新しいアルゴリズム等を試す際にも使える。

この評価方法はクロスバリデーションセットでやるべきである。テストセットで行うのは適切でない。

まとめると
- まずは汚い実装をできる限り素早く行う。この実装を元にエラー分析などを行い次に何をすべきかのヒントを得ることができる。
- 単一実数の評価指標を用意することで様々なアイデアを試してその効果を比べることができる。