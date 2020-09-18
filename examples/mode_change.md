---
layout: default
title: 複数のアニメーションの切替え
parent: サンプルコード
nav_order: 7
---

# 複数のアニメーションの切替え

数字キー\(1or2\)を押すことで、アニメーションを切り替える

```java
int mode = 1;

void setup(){
  size(500,400);
}

void draw(){
  if(mode == 1){
    line(0,random(height), width, random(height));
  }else if(mode == 2){
    ellipse(width/2, height/2, random(width), random(height));
  }
}

void keyPressed() {
  if (key == '1') {
    mode = 1;
  }else if(key == '2'){
    mode = 2;
  }
  background(204);
}
```

さらに三つのモードを切り替えるサンプルもポストしておく↓

```java
int mode = 1;

float dia = 0;

void setup(){
  fullScreen();
  noFill();
  strokeWeight(4);
  smooth();

  rectMode(CORNERS);
}

void draw(){
  background(204);
  if(mode == 1){
    //scene01
    dia = random(height);
    ellipse(random(width), random(height), dia, dia);
  }else if(mode == 2){
    //scene02
    rect(width/2,height/2,random(width),random(height));
  }else if(mode == 3){
    //scene03
    strokeWeight(random(20));
    line(0,random(height),width,random(height));
  }
}

void keyPressed(){
  if(key == '1'){
    mode = 1;
  }else if(key == '2'){
    mode = 2;
  }else if(key == '3'){
    mode = 3;
  }
}
```
