---
layout: default
title:  randomでサイコロ
parent: Random - 乱数
nav_order: 1
---

# random()をサイコロとして使う

**(int)random( 出て欲しい目の数 ) % 出て欲しい目数**

と書くとランダム関数をサイコロとして使える。
("%"は割り算ではなくて、余りを返す。)

### 例：通常の６面サイコロとして使う場合。
```java
int answer = (int)random(6) % 6;
```

※この場合変数answerに入るのは、0～5までの整数のどれかになる。

### サンプル01
ランダムで丸か四角を中央に描く。(実行するたびに結果が違う)

```java
int dice = 0;

void setup(){
  size(800,800);
  noLoop();

  rectMode(CENTER);
  ellipseMode(CENTER);
}

void draw(){
  dice = (int)random(2)%2;

  if(dice == 0){
    rect(width/2, height/2, 400, 400);
  }else if(dice == 1){
    ellipse(width/2, height/2, 400, 400);
  }

}
```

### サンプル02
↑の応用で、縦横に10x10でランダムに丸か四角を並べる
```java
int dice = 0;
int x = 0;
int y = 0;


void setup() {
  size(800, 800);
  noLoop();

  rectMode(CENTER);
  ellipseMode(CENTER);
}

void draw() {

  for (int j=0; j < 10; j++){
    for (int i=0; i < 10; i++){
      x = width/10*i + width/20;
      y = height/10*j + height/20;
      dice = (int)random(2)%2;
      if (dice == 0) {
        rect(x, y, 50, 50);
      } else if (dice == 1) {
        ellipse(x, y, 50, 50);
      }
    }
  }
}
```

#### あとはサイコロの出目で色を変えたり、大きさ変えたり、色々使える...
