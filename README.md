# Two-LED-Operation

ロボットシステム学の課題として製作したものです。

1つのプログラムで2つのLEDを制御することができます。

## デモ動画
　[点灯・消灯動作](https://www.youtube.com/watch?v=dCKD5hGhAEE)

## 準備するもの
* raspberrypi3  
* ブレッドボード  
* 330Ω抵抗 × 2  
* LED × 2  

## raspberry pi3との接続方法
準備するものに書かれてたものを以下のように繋げてください。

pin20 ------- [330] ---- [LED] ------ GND  
  
pin25 ------- [330] ---- [LED] ------ GND

330 = 330Ωのことです。
GNDは共通であっても、別々でも大きな影響はありません。

## 実行までの手順
* リポジトリをクローンします  
`https://github.com/Shimataku9311/Two-LED-Operation.git`
* 以下の方法でコンパイルとカーネルモジュールロードを実行します  
`cd Two-LED-Operation`  
`make`  
`sudo insmod myled.ko`  
`sudo chmod 666 /dev/myled0`  
* カーネルモジュールのアンマウント方法は以下の方法で出来ます  
`sudo rmmod myled0`  
* LED点灯・消灯は以下の方法で出来ます  
`echo 0 > /dev/myled0 //両LED消灯`  
`echo 1 > /dev/myled0 //pin20側のLEDを点灯`  
`echo 2 > /dev/myled0 //pin25側のLEDを点灯`  
`echo 3 > /dev/myled0 //pin20側のLEDを消灯`  
`echo 4 > /dev/myled0 //pin25側のLEDを消灯`  
