# Color : 色

手始めに背景色を変更してます。

```java
size(500,400);  //set canvas size as 500x400 

//set background color by gray scale 0~255
background(60); 

//set background color by RGB 0~255
//background(181,75,72);

//set back ground color by hex color code
//background(#11B773);
```
######※コメント部分で無効にされているコードを有効にすると違いが見れます。

↓そのまま実行した結果

![](/assets/background_run.png)

**background()**関数は指定した色を背景色にします。
指定の仕方は複数あり...

•グレースケールで指定(値:0~255)
**background(Grayscale)**

•RGBで指定(値:0~255)
**background(R,G,B)**

•HEXカラーコードで指定(ツール >　色選択　を使うと便利)
**background(HEX)**