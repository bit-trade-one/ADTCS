# 超小型USBタッチスイッチファームウェア

## ファイルリスト

 - ADTCS_v001.zip

超小型USBタッチスイッチののファームウェアと、
Microchip社のファームウェア書込ツールを公開しています。 

## ファームウェア書込ツール（HIDBootLoader.exe）の使い方

### 1. このソフトで何が出来るのか

超小型USBタッチスイッチはMicrochip社のPICと言うマイコンを用いて作られています。  
通常、PICマイコンにソフトを書き込む為には「ライタ」と呼ばれる書き込み装置が必要です。  
（Microchip社が出しているPICkitや、秋月電子のキットであるAKI-PICプログラマーなどが有名です）  

このソフトを用いれば、特別なライタを必要とせず、USBから直接マイコンのソフトを書き換える事ができます。  
ただし、その為にはマイコンにBootLoaderと呼ばれる特別なソフトがあらかじめ書き込まれている必要があり、またUSB経由で書き込むソフトもBootLoaderに対応したものになっていなければなりません。  
あらかじめ書き込まれるBootLoader自体は、「ライタ」で書き込まなければなりません。  

超小型USBタッチスイッチに付属しているマイコンにはこのBootLoaderと言う特別なソフトがあらかじめ書かれています。よって、特別なライタをお持ちでなくてもUSB経由でソフトを書き込むことができます。  
また、GitHubで公開されている超小型USBタッチスイッチ用のソフトはこのBootLoaderでの書き込みに対応したソフトになっています。  

このBootLoaderを使うことで、USB経由で簡単にソフトを書き換えて、REVIVE USBのソフトを様々に書き換える事ができます。  

### 2. 準備

[こちら](https://github.com/bit-trade-one/REVIVE-USB-MICRO/raw/master/Writing-Tool/HIDBootLoader.exe)からHIDBootLoader.exeをダウンロードします。  
（これは、Microchipさんが公開しているライブラリ「MCHPFSUSB」の中にある物と同一です）  

このソフトは.NET framework 2.0を用いて作成されています。  
お手持ちのパソコンに.NET frameworkがインストールされていない場合、MicrosoftさんのHPからこれらをダウンロードし、インストールしておく必要があります。  
“Microsoft .NET framework”等のキーワードで検索すると出てきます。  

書き込みたいソフトもダウンロードしておきます。  

### 3. ソフトの書き込み

最初に、設定ツールから超小型USBタッチスイッチをBOOTモードにします。
![](https://bit-trade-one.co.jp/wp/wp-content/uploads/2020/06/ADTCS02Update.png)  
右下の「Update」ボタンをクリックしてください。
![](https://bit-trade-one.co.jp/wp/wp-content/uploads/2020/06/ADTCS03dialog.png)  
するとこのようにダイアログが表示されます。
OKをクリックすると、超小型USBタッチスイッチがBOOTモードになります。

HIDBootLoader.exeを立ち上げます。  

![](http://bit-trade-one.co.jp/wp/wp-content/uploads/2019/06/03HIDTool.png)  
デバイスが認識されると上図の様に「Device attached」と表示されます。  
初めてBOOTモードで接続した時には、自動的にPCにドライバがインストールされます。（約１分程時間かかります）  

「Open Hex File」を押します。  
書き込みたいHexファイルを選択します。  
![](https://bit-trade-one.co.jp/wp/wp-content/uploads/2020/06/ADTCS05select.png)  
「Program/Verify」を押します。
ソフトが書き込まれます。  
![](http://bit-trade-one.co.jp/wp/wp-content/uploads/2019/06/05Program.png)  
USBケーブルを抜き差しすると、書き込んだソフトが起動します。  
