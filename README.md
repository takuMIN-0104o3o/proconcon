## proconcon
スプラトゥーン3 マウスコンバーター  

## 初期設定
echo "dtoverlay=dwc2" | sudo tee -a /boot/config.txt
echo "dwc2" | sudo tee -a /etc/modules
echo "libcomposite" | sudo tee -a /etc/modules
sudo python -m pip install joycon-python hid pyglm keyboard
sudo apt install git -y
sudo git clone https://github.com/takuMIN-0104o3o/proconcon.git /root/proconcon


## ビルド方法
gcc proconcon.c -o proconcon.out -l pthread -lm -O3 -Wall  
  
キーボード、マウスの選択はソースコードに記載があります。  
各自のデバイス名に合わせてください。  
  
## 接続方法
ラズベリーパイにKeyboard、Mouseを接続する。  
ラズベリーパイをUSBケーブルでNintendo SWITCHに接続する。  
  
## 起動方法
sudo ./load_procon.sh  
sudo ./proconcon.out  

**proconcon.outと同じ場所にflashrom.binを配置してください。**  
**flashrom.binはコントローラーの設定ファイルで、proconcon.out起動時に利用します。** 
  
マウス感度は800-1600 DPIをあたりで調整すると良さそうです。  
本プログラムはCUI(CLI)で利用してください。  
デスクトップ環境では本プログラム使用中に範囲外のクリックなどが発生し、誤動作の原因になります。  
![IMG_E1374](https://user-images.githubusercontent.com/83897755/204680187-3678ed45-c9b6-499e-8ff4-b0cc18fd81f5.jpg)  
    
## センターリング  
試合が始まった時、1キーを1秒ほど間隔を開けて2回押してください。  
この操作で、マウスのセンターリングが行われます。  
もし、マウスの動きがゲームに正しく反映されない場合は再度センターリングを行ってください。  

## ボタン配置
デフォルト状態では下記のキー配置になっています。  

| Key           | ProCon        | Comment                                           |  
| ------------- | ------------- | ------------------------------------------------- |  
| ESC           | Home          |                                                   |
| 1             | Y             | Centering                                          |  
| 2             | Capture       |                                                   |  
| 3             | -             |                                                   |  
| 4             | +             |                                                   | 
| 7             |               | Rapid Fire (Slow)                                 |
| 8             |               | Rapid Fire (High)                                 |
| 9             |               | Mouse Lの単射、連射入れ替え                        | 
| WASD          | Stick L       |                                                   | 
| SHIFT L       |               | Move slowly with SHIFT L + WASD                   | 
| SPACE         | B             |                                                   |
| E             | A             |                                                   | 
| R             | X             |                                                   | 
| F             | Hat Up        |                                                   | 
| C             | Hat Down      |                                                   | 
| T             | L             |                                                   | 
| Y             | R             |                                                   | 
| G             | ZL            | Added in ver 0.16                                 | 
| H             | ZR            | Added in ver 0.16                                 | 
| U             | Stick L Push  |                                                   | 
| I             | Stick R Push  |                                                   | 
| L             |               | Tesla menu open                                   | 
| Z             |               | Super jump to respawn point                     | 
| Num2          | Hat Down      |                                                   | 
| Num4          | Hat Left      |                                                   | 
| Num6          | Hat Right     |                                                   | 
| Num8          | Hat Up        |                                                   | 
| Arrow Key     | Stick R       |                                                   | 
| F5            |               | X sensitivity+0.1 デバッグ用                       | 
| F6            |               | X sensitivity-0.1 デバッグ用                       | 
| F7            |               | Y sensitivity+0.1 デバッグ用                       | 
| F8            |               | Y sensitivity-0.1 デバッグ用                       | 
| F9            |               | Y following+0.1 デバッグ用                       | 
| F10           |               | Y following-0.1 デバッグ用                       | 
| Mouse R       | R             |                                                   | 
| Mouse L       | ZR            |                                                   | 
| Mouse Side    | ZL            |                                                   | 
| Mouse Extra   | ZR            | Rapid Fire                                       | 
| Mouse Wheel   | Stick R Push  |                                                   | 
| Mouse Middle  | Stick R Push  |                                                   | 
| Mouse move    | Gyro          |                                                   | 

  
## 参考文献
https://www.mzyy94.com/blog/2020/03/20/nintendo-switch-pro-controller-usb-gadget/  
https://github.com/dekuNukem/Nintendo_Switch_Reverse_Engineering  
