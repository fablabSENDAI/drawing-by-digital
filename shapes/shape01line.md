---
layout: default
title: Shape01 - 線を引く
parent: Shapes - 図形
nav_order: 2
---

# Shape01:線を引く

続けて、２行目を見ていきましょう

```java
size(500,400);

line(0,200,500,200);　// <-　２行目
```

先ほどと同じく、分からない関数があったらProcessingのリファレンスページを見てみます。  
[line\(\)のページ](https://processing.org/reference/line_.html)を見てみると以下のように書かれております

<img src="../assets/line_ref.png" alt="hi" class="inline"/>

**Description**によるとline\(\)はその名の通り、線を引くため関数で\(\)内に２点のxy座標を入れるとその点同士を結ぶ直線を引いてくれます。  
\(今は2Dグラフィックのモードなので、Z座標は無視します。\)

また、Processingのウィンドウでは...  
**左から右：X軸方向  
上から下：Y軸方向**  
となっています。なので、

```java
line(0,200,500,200);
```

と書くと以下のようになります。

<img src="../assets/line_run_line.png" alt="hi" class="inline"/>

ウィンドウの左上が原点\(0,0\)であり、\(0,200\)から\(0,500\)まで直線が引かれております。

Y軸方向のウィンドウサイズはsize\(\)により400で作られているので、

ウィンドウのちょうど中間に線が引かれていますね。
