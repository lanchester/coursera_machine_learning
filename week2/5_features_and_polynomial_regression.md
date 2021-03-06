# 多項式回帰

<img width="720" alt="2016-07-04 16 53 01" src="https://cloud.githubusercontent.com/assets/6447085/16554116/cc6b52ee-4207-11e6-8aa8-8cef08245369.png">

線形回帰を適用する際にはすべてのフィーチャーを使用し無くてはならないというわけではありません。既存の2つのフィーチャーから新たに1つのフィーチャーを定義してそれを代わりに使用することもできます。

<img width="722" alt="2016-07-04 17 10 46" src="https://cloud.githubusercontent.com/assets/6447085/16554512/4848ccdc-420a-11e6-9724-14b7417c529c.png">

直線の代わりに二次曲線やさらに高次の曲線を代わりに使うこともできます。これを多項式回帰と言います。ここまでに学習した線形回帰のアルゴリズムを少し改変することでこれに対応することができます。

<img width="760" alt="2016-07-04 18 47 02" src="https://cloud.githubusercontent.com/assets/6447085/16556934/c98fb64a-4217-11e6-9696-a713676550f0.png">

仮説を選ぶ場合にはいくつかフィットしそうな関数を知っておくと良いでしょう。上記の場合、 $\sqrt[]{x}$ の関数は単調増加で、二次関数のように戻ってくることがないのでより適しているといえます。

##### フィーチャー選択アルゴリズム
ここまで、フィーチャーを選ぶ際には単に提示されているフィーチャー以外にも様々な選択肢がありました。どのようにフィーチャー選定すべきかは難しい問題ですがこれを自動的に決定するアルゴリズムも存在します（クラスの後半に議論します）。これによって直線にかぎらず複雑な関数、多項式に当てはめることが出来るフィーチャーを決定することができます。
