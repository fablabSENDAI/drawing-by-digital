---
layout: default
title: Animation01 - for文
parent: Animation - 動き
nav_order: 2
---

#Animation01:for文

まずは、画面の真ん中で伸縮を繰り返す円を描きます。
```java
//Example: single

int x = 0;

void setup(){
  size(500,400);
}

void draw(){
  background(204);

  x = x + 1;

  if(x >= 50){
    x = 0;
  }

   ellipse(250,200,x,x);
}
```
実行結果↓
![](/assets/single_run.png)

#for文
for文を使えば任意の命令を好きな回数だけ繰り返すことができます
```java
  for(変数;条件;処理){
    •••条件から外れるまで、ここの命令が繰り返されます•••
  }
```
これを使って先程のボールを横一列に並べます。
```java
//Example: multiple

int x = 0;

void setup(){
  size(500,500);
}

void draw(){
  background(204);

  x = x + 1;

  if(x >= 40){
    x = 0;
  }

  for(int i=0; i < 9; i++){
    ellipse(i*50+50, 250, (x+i*4)%41, (x+i*4)%41);
  }
}
```
実行結果↓
![](/assets/multi_run.png)
######※ %で割ることで、伸縮の周期をずらしています

###縦方向にも並べる
横に並んだボールの行を今度は縦に並べてみます。
for文の中にfor文を書きます。

```java
Example: matrix

int x = 0;

void setup(){
  size(500,500);
}

void draw(){
  background(204);

  x = x + 1;

  if(x >= 40){
    x = 0;
  }

  for(int i=0; i < 9; i++){
    for(int j=0; j < 9; j++){
      ellipse(i*50+50, j*50+50, (x+(i+j)*4)%41, (x+(i+j)*4)%41);
    }
  }
}
```
実行結果↓
![](/assets/matrix_run.png)
