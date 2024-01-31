# RGB bottom for ATOM-HSBL-S100-01 


## 購入
[こちら](https://sites.google.com/view/hsbl-s100/home#h.4ybfc96k160s)から

## 概要

M5 ATOMデバイスの底面にRGB機能を追加します。  
  
RGBLEDのシリアル通信PINはATOMS3の場合PIN6にデフォルトで接続され、  
ハンダジャンパによりPIN5,PIN7に切り替えが可能です。(その場合JP6はカットしてください。)  

<img src="https://github.com/HSBL-ko-gyo/HSBL-S100-01/assets/128065816/79a9aaa9-b3f0-487e-90e0-33cfae15e57a" width="300" >


## WEB tool

ATOMS3で使用する場合、OSSの[HSBL-S101 Chameleon WEBtool](https://hsbl-ko-gyo.github.io/HSBL-S101/)にて  
RGBの色の変更がブラウザから可能です。  
ファームウェア書き込みも同ページより可能です。  

## サンプルコード

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
