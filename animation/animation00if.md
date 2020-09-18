---
layout: default
title: Animation00 - if文
parent: Animation - 動き
nav_order: 1
---

#Animation00:if文
if文はある条件をみたすときだけ命令を行うような時に役立ちます。
```java
if(条件){
    •••ここは条件を満たすときだけ実行される•••
}
```
これを使ってボールがウィンドウの右恥まで行くと跳ね返るように書き換え

```java
//Example: return

int x = 0;
int dir = 5;

void setup(){
  size(500,400);
}

void draw(){
  //background(204);
  ellipse(x,200,100,100);
  x = x + dir;
  if(x >= 500){
    dir = dir * -1;
  }
}
```

###バウンド
さらに右端だけでなく左端にボールが来た際にもバウンドするようにして、行ったり来たりを繰り返すようにします

```java
//Example: repeat

int x = 0;
int dir = 5;

void setup(){
  size(500,400);
}

void draw(){
  //background(204);
  ellipse(x,200,100,100);
  x = x + dir;
  if(x >= 500){
    dir = dir * -1;
  }
  if(x <= 0){
    dir = dir * -1;
  }
}

```
