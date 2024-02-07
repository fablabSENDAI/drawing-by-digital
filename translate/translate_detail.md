---
layout: default
title: Translate - 原点を動かす
parent: 原点座標の変更
nav_order: 1
---

# Translate - 原点を動かす

**translate()** 関数は、原点の位置を移動させる機能を持つ。
**translate(X方向の移動距離, Y方向の移動距離);**
※座標を指定するのではなく、移動距離を指定しているの注意！

まずは、下のプログラムを実行してみよう。
```java
void setup() {
  size(500, 400);
}

void draw() {
  //白い円
  fill(255);
  ellipse(0, 0, 200, 200);

  translate(250, 200); //原点をキャンバス中心に移動
  //ここは、　translate(width/2, height/2); とも書けるね

  //黒い円
  fill(0);
  ellipse(0, 0, 200, 200);
}
```
実行結果は、こうなる。


<img src="../assets/translate01.png" alt="hi" class="inline"/>

どちらの円も指定座標は、**(0,0)** つまり原点中心。

なので、白い円は左上角（元々の原点）を中心に描かれているため画面外にはみ出してしまう。

しかし、黒い円は白い円と全く同じ位置指定にもかかわらず、キャンバスの真ん中に描かれている。


これは、途中に使われている **translate()** 関数が原点を下の図のように移動した為に起こっている。

<img src="../assets/translate02.png" alt="hi" class="inline"/>


## 座標指定ではなく、移動距離

次に、別のサンプルを見てみよう
```java
void setup() {
  size(500, 400);
}

void draw() {
  rect(0,0,50,50);
  translate(100,100);
  rect(0,0,50,50);
  translate(100,100);
  rect(0,0,50,50);
  translate(150,0);
  rect(0,0,50,50);
  translate(0,-150);
  rect(0,0,50,50);
}
```

実行結果はこうなる↓

<img src="../assets/translate03.png" alt="hi" class="inline"/>

translate()の中身は座標指定ではなく、原点をX方向そしてY方向にどれだけずらすか（移動量）であることに注意しよう。


<img src="../assets/translate04.png" alt="hi" class="inline"/>