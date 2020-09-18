---
layout: default
title: Minim
parent: Library : ライブラリ
nav_order: 2
---

#Minim
Minim(ミニム)はサウンドの出力•入力を可能にするライブラリで、
•mp3音源の再生
•入力された音の波形表示
•FFT解析(音の成分分析)
などが簡単に行えるようになります

###FFT解析(高速フーリエ変換)
入力された音の中にどれだけ高音、または低音が含まれているかを分析する手法の１つで、これを利用する事で曲調や楽器に合わせたグラフィックが作れるようになります
とりあえず、まずはサンプルをみてみましょう↓

```java
//Example: FFT

import ddf.minim.analysis.*;
import ddf.minim.*;

Minim minim;

AudioInput in; //Audio Input
FFT fft; //FFT class

void setup() {
  size(1024, 400);
  //Minim init
  minim = new Minim(this);
  //stereo input
  in = minim.getLineIn(Minim.STEREO, 512);
  //FFT init
  fft = new FFT(in.bufferSize(), in.sampleRate());
  //set analyze window as HAMMING
  fft.window(FFT.HAMMING);
}

void draw() {
  background(0);
  stroke(255);

  //FFT
  fft.forward(in.mix);

  //draw graph
  for (int i = 0; i < fft.specSize(); i++) {
    float x = map(i, 0, fft.specSize(), 0, width);
    line(x, height, x, height - fft.getBand(i) * 8);
  }
}

void stop() {
  minim.stop();
  super.stop();
}
```
実行結果↓
![](/assets/fft_run.png)
