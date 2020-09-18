---
layout: default
title: Animation - 動き
nav_order: 9
has_children: true
---

# Animation : 動き

まずは自動で一直線に動く、ボールを作ってみる。

```java
//Example: one way

int x = 0;

void setup(){
  size(500,400);
}

void draw(){
  //background(204);
  ellipse(x,200,100,100);
  x = x + 1;
}
```
