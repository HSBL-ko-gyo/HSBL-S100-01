## RGB LED bottom for ATOM HSBL-S100-01 
<img src="https://github.com/HSBL-ko-gyo/HSBL-S100-01/assets/128065816/71b2e537-0d9a-48d0-b707-0dc9a187bdfa" width="300" >



### 購入

<a href="https://sites.google.com/view/hsbl-s100/home#h.4ybfc96k160s" target="_blank">購入先一覧</a>


### 概要

M5 ATOMデバイスの底面にRGB機能を追加します。  
  
RGBLEDのシリアル通信PINはATOMS3の場合PIN6にデフォルトで接続され、  
ハンダジャンパによりPIN5,PIN7に切り替えが可能です。(その場合JP6はカットしてください。)  

<img src="https://github.com/HSBL-ko-gyo/HSBL-S100-01/assets/128065816/79a9aaa9-b3f0-487e-90e0-33cfae15e57a" width="300" >

### 回路

<a href="https://github.com/HSBL-ko-gyo/HSBL-S100-01/tree/main/circuit" target="_blank">HSBL-S100-01/circuit/</a>


### WEB ツール

ATOMS3で使用する場合、OSSの<a href="https://hsbl-ko-gyo.github.io/HSBL-S101/" target="_blank">HSBL-S101 Chameleon WEBtool</a>にて  
RGB色の変更がブラウザから可能です。  
ファームウェア書き込み機能も同ページより提供しています。  


### サンプルコード

``` C++
#include <Adafruit_NeoPixel.h>

#define PIN        6  // ネオピクセルが接続されているピン
#define NUMPIXELS  1  // ネオピクセルの数

// NeoPixelオブジェクトを作成
Adafruit_NeoPixel pixels(NUMPIXELS, PIN, NEO_GRB + NEO_KHZ800);

void setup() {
  pixels.begin(); // NeoPixelの初期化
}

void loop() {
  pixels.setPixelColor(0, pixels.Color(255, 0, 0)); // 赤色
  pixels.show();
  delay(500);

  pixels.setPixelColor(0, pixels.Color(0, 255, 0)); // 緑色
  pixels.show();
  delay(500);

  pixels.setPixelColor(0, pixels.Color(0, 0, 255)); // 青色
  pixels.show();
  delay(500);
}
```
