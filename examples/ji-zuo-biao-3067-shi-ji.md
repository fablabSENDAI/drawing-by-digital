---
layout: default
title: 極座標で描く
parent: サンプルコード
nav_order: 5
---

# 極座標で時計

平面での位置の表し方には、
X要素とY要素で座標を表す[直交座標](https://ja.wikipedia.org/wiki/%E7%9B%B4%E4%BA%A4%E5%BA%A7%E6%A8%99%E7%B3%BB)と、

原点からの角度Θと距離rで座標を表す[極座標](https://ja.wikipedia.org/wiki/%E6%A5%B5%E5%BA%A7%E6%A8%99%E7%B3%BB)がある。

直交座標は、モノを縦横グリッドに並べるのに向いていて、
極座標は環状に並べる時に向いてる。


### サンプルコード1(丸を丸く並べる)

```java
float y = 0;
int ball_num = 12;

void setup(){
  size(600, 400);
  noLoop();
}

void draw(){
  background(204);

  for(int i=0; i < ball_num; i++){
    x = r*cos(2*PI/ball_num*i) + width/2;
    y = r*sin(2*PI/ball_num*i) + height/2;
    ellipse(x, y, 50, 50);
  }
}
```


### サンプルコード2(時計)

```java
float theta = PI/2; // 0 ~ PI*2
float r = 200; //distance
float x = 0;
float y = 0;

void setup(){
  size(600, 400);

}

void draw(){
  background(204);

  theta = theta + PI/60;
  if(theta >= PI*2){
    theta = 0;
  }

  x = r*cos(theta) + width/2;
  y = r*sin(theta) + height/2;
  line(width/2, height/2, x, y);
}
```
