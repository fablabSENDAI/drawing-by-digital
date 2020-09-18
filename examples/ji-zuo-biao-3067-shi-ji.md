#極座標で時計

###サンプルコード

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