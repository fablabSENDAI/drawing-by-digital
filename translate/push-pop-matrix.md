---
layout: default
title: Push MatrixとPop Matrix - 原点位置の保存と読み出し
parent: 原点座標の変更
nav_order: 2
---

# Push MatrixとPop Matrix - 原点位置の保存と読み出し

例えば、下のような図形をタテヨコにグリッドに並べる。

<img src="../assets/pop_push_matrix01.png" alt="hi" class="inline"/>


これは、vertex()を用いて、次のようなコードで描かれている。


```java
void setup() {
  size(80, 80);
}

void draw() {
  //逆三角形描画
  beginShape();
  vertex(0, 0);
  vertex(80, 0);
  vertex(40, 80);
  endShape(CLOSE);
}
```

これを、[前にやった方法](../animation/animation01for.md)でグリッドに並べようとすると、

**vertex()** のX,Y座標の中身を全部計算式に置き換えないといけないので、面倒くさい。

そこで **translate()** で、原点位置をずらして、スタンプを押す位置を変えていくが如くグリッド上に並べてみたいと思う。

ただ、 **translate()** は前のページでも言った通り、原点が今いる所からの移動量を受け取るので、

座標指定を繰り返していくとドンドンずれていってしまう。

なので今回は、

translate()で三角形を書きたい所に原点移動<br>
↓<br>
vertex()で三角形描画<br>
↓<br>
原点をキャンバス左上角(元々の原点位置)に移動して<br>
↓<br>
translate()で次の三角形を書きたい所に原点移動<br>
↓<br>
以下、同様に繰り返し

というふうにグリッドを描いていこうと思う。

そこで役に立つのが **popMatrix()** と **pushMatrix()** という関数だ。<br>
簡単に説明すると、

**popMatrix() : 今の原点位置を記録　セーブみたいなもん**

**PushMatrix() : popMatrix()で記録された位置に原点を戻す　ロードみたいなもん**

という感じ。<br>
これを使って、グリッドに並べるプログラムを書くとこうなる。

```java
void setup() {
  size(800, 800);
}

void draw() {

  for (int j = 0; j < 10; j++) {
    for (int i = 0; i < 10; i++) {
      pushMatrix(); //キャンバスのオリジナル原点を記録
      translate(80*i, 80*j); //iとjの数値によって原点をX方向とY方向にずらす

      //逆三角形描画
      beginShape();
      vertex(0, 0);
      vertex(80, 0);
      vertex(40, 80);
      endShape(CLOSE);

      popMatrix();  //オリジナル原点に復帰
    }
  }
}
```

これの結果画面はこうなる↓

<img src="../assets/pop_push_matrix02.png" alt="hi" class="inline"/>

便利な機能だが、popMatrix()で記録された原点位置を１回読みだすと、記録が消えてしまうので注意。<br>
ロードしたら消えてしまうセーブデータだと思ってくれるといいだろう。<br>