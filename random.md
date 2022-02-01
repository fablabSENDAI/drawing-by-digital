---
layout: default
title: Random - 乱数
nav_order: 10
has_children: true
---

# Random : 乱数

random()は指定した範囲からランダムに数を出力してくれる関数です。

##### 例：
random(80)とすると、0 < = 出力する値　< = 80

random(80,100)とすると、80 < = 出力する値　< = 100

これを使って、ランダムに線を引くプログラムを組んでみます。

```java
//Example: random

void setup(){
size(500,400);
}

void draw(){
  line(0,random(height), width, random(height));
}
```
