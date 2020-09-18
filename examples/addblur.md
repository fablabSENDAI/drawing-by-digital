# 残像\(ブラー\)を残す

background\(\)ではなくて、rect\(\)で全体を塗りつぶすことで、  
動きにブラーをかけます。  
  
###サンプルコード
```java
void setup(){
  size(500,400);
}

void draw(){
  noStroke();
  fill(204,40);
  rect(0,0,width,height);
  
  stroke(0);
  fill(255);
  ellipse(mouseX, mouseY, 100, 100);
}
```
