---
layout: default
title: FFTの要素１つの強さを円の塗りに反映
parent: サンプルコード
nav_order: 4
---

# FFTの要素を１つだけ取り出して、その要素の強さを円の塗りに反映します。

```java
import ddf.minim.analysis.*;
import ddf.minim.*;

Minim minim;

AudioInput in; //オーディオ入力
FFT fft; //FFTクラス

void setup() {
  size(1024, 400);
  //Minim初期化
  minim = new Minim(this);
  //ステレオでオーディオ入力
  in = minim.getLineIn(Minim.STEREO, 512);
  //FFTを新規に行う
  fft = new FFT(in.bufferSize(), in.sampleRate());
  //分析窓は、ハミング窓で
  fft.window(FFT.HAMMING);
}

void draw() {
  background(0);
  stroke(255);

  //FFT変換実行
  fft.forward(in.mix);

 /*
  //グラフ生成
  for (int i = 0; i < fft.specSize(); i++) {
    float x = map(i, 0, fft.specSize(), 0, width);
    line(x, height, x, height - fft.getBand(i)*8);
  }*/

  //fft.getBand()に入れる値は、0(最低音)〜526(最高音)
  fill(fft.getBand(120)*10);
  ellipse(width/2, height/2, 200, 200);

}

void stop() {
  minim.stop();
  super.stop();
}
```
実行結果↓
