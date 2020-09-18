---
layout: default
title: Ani
parent: Library - ライブラリ
nav_order: 1
has_children: true
---

# Ani

動きや色の数値の変化のスピードをコントロールするためのライブラリ。

### イージング\(Easing\)

単調な等速運動ではなく、動きに緩急をつけることで質感や意味を持たせることができます。

以下はAniライブラリの基本的な使い方を体験できるサンプルコードです。

```java
//example for using Ani to contorol easing, motion
import de.looksgood.ani.*;

float x = 256;
float y = 256;
int diameter = 50;

void setup() {
  size(512,512);
  smooth();
  noStroke();

  // you have to call always Ani.init() first!
  Ani.init(this);
}

void draw() {
  background(255);
  fill(0);
  ellipse(x,y,diameter,diameter);
}

void mouseReleased() {
  //you can change easing style with Ani.XXX here
  Ani.to(this, 1.0, "x", mouseX, Ani.SINE_OUT);
  Ani.to(this, 1.0, "y", mouseY, Ani.SINE_OUT);
}
```

コード中の下記の部分で、ボールが滑らかに動くように命令しています。

```java
  Ani.to(this, 1.0, "x", mouseX, Ani.SINE_OUT);
  Ani.to(this, 1.0, "y", mouseY, Ani.SINE_OUT);
```

Ani.to\(\)という命令をもう少し詳しく説明すると

**Ani.to\(this\(ここはそのまま\), アニメーションの時間, "数値を変えたい変数", 目標値, イージングの種類\)**

となっていて、上記のコードだとアニメーション時間"1.0"となっているため、渡した変数の値が現在の数値から目標値まで1.0秒かけて変化するようになっています。



また、イージングの種類を変えることで動き方が変わります。イージングの種類は以下のとおりになります↓

**Ani.LINEAR**

**Ani.QUAD\_IN**

**Ani.QUAD\_OUT**

**Ani.QUAD\_IN\_OUT**

**Ani.CUBIC\_IN**

**Ani.CUBIC\_OUT**

**Ani.CUBIC\_IN\_OUT**

**Ani.QUART\_IN**

**Ani.QUART\_OUT**

**Ani.QUART\_IN\_OUT**

**Ani.QUINT\_IN**

**Ani.QUINT\_OUT**

**Ani.QUINT\_IN\_OUT**

**Ani.SINE\_IN**

**Ani.SINE\_OUT**

**Ani.SINE\_IN\_OUT**

**Ani.CIRC\_IN**

**Ani.CIRC\_OUT**

**Ani.CIRC\_IN\_OUT**

**Ani.EXPO\_IN**

**Ani.EXPO\_OUT**

**Ani.EXPO\_IN\_OUT**

**Ani.BACK\_IN**

**Ani.BACK\_OUT**

**Ani.BACK\_IN\_OUT**

**Ani.BOUNCE\_IN**

**Ani.BOUNCE\_OUT**

**Ani.BOUNCE\_IN\_OUT**

**Ani.ELASTIC\_IN**

**Ani.ELASTIC\_OUT**

**Ani.ELASTIC\_IN\_OUT**

\(詳しくは、[イージングの種類](/library--ライブラリ/ani/30a4-30fc-30b8-30f3-30b0-306e-zhong-lei.md)のページを参照\)
