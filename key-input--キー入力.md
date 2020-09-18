# Key Input : キー入力
キーボードの入力によって、ボールの色が変わるようにします。
```java
// Example: key_press

int value = 0;

void draw() {
  fill(value);
  rect(25, 25, 50, 50);
}

void keyPressed() {
  if (value == 0) {
    value = 255;
  } else {
    value = 0;
  }
} 
```
実行結果↓
![](/assets/key_input.png)

###押されたキーを判別する
あらかじめProcessing側で用意されている変数**key**にはタイプされたキーボードの文字が入っています。これとif文を利用してタイプされた文字に対して別々に反応するようなプログラムを書いてみましょう

```java
//Example: key value

int value = 0;

void draw() {
  fill(value);
  rect(25, 25, 50, 50);
}

void keyPressed() {
  if (key == 'b') {
    value = 0;
  }else if(key == 'w'){
    value = 255;
  }else{
    value = 127;
  }
}
```


