# Welcome to sugiuraii.github.io front page.

# Websocket automotive gauge project.
![Websocket gauge diagram](./car-dashboard_test1.svg)

## 概要
* これは何？
	* 車のセンサ情報（車速・回転数・水温・ブースト等）を取得して、グラフィカルなメーターとして表示するアプリ。

* 特徴
	* センサ情報を集めて配信するサーバーと、サーバーから配信されたセンサ情報をメーターとして表示を担当するクライアントに分かれている。
	* サーバーとクライアント間の通信はWebsocketを使用。IPが通ればよいが通常は有線LANかWifiで繋げる。

* クライアント側の特徴
	* クライアントはWebアプリであり、ブラウザが動けばOSはなんでもよい（PCであってもスマホであっても）インストールも不要。
	* クライアントは複数台あってもよい（スマホを複数用意して、各々別のメーターを表示させることが可能。
	* クライアントのグラフィック表示はWebGLを使用しており、Webベースでありながら割と高速。(ほとんどpixi.jsのおかげ）
	* クライアントのjavascript(typescript)のソースコードをいじることで、自分でメーターデザインを変更することが可能。

* サーバー側の特徴
	* サーバー側もマルチプラットフォーム対応しており、.net(6.0)+asp.netが動きシリアルポートへのアクセスができれば、OSやCPUは問わない（はず）
	* Windows+x64、Linux+x64、Linux+ARMで動作確認。Raspberry Piでも動作可能。

![接続図](./WebsocketGaugeDiagram.png)

## とりあえず試してみる.
[Quick start](WebsocketGauge/docs/QuickStart_jpn.md)を参照ください。

## メーターをデザインしてみる
こちらのレポジトリを参照ください。 [WebSocketGaugeClientNeo](https://sugiuraii.github.io/WebSocketGaugeClientNeo/).

## デモ動画.
### Demonstration on car
<iframe width="640" height="360" src="https://www.youtube.com/embed/QCOYLCIrU_s" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Demonstration on development PC
<iframe width="640" height="360" src="https://www.youtube.com/embed/pAk8FpmZctI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Arduino sensor unit demo.
<iframe width="640" height="360" src="https://www.youtube.com/embed/HvkB07k6gMc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### ELM327 demo (emulated on obdsim)
<iframe width="640" height="360" src="https://www.youtube.com/embed/l_niGjlkpQ4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## Gallery
* アナログ3眼メーター
![AnalogTripleMeter](./TripleAnalogMeter.png)
* Multi function display (MFD)
![MFD](./MFDScreenShot.png)
* メーターとカーナビ(Picture-in-picture)
	* Using Android multiple window separation feature
![PictureInPicture](./MeterWithPictureInPicture.jpg)
* メーターとカーナビ(ウィジェット)
	* メーターウィジェット化のために [Overlays](https://play.google.com/store/apps/details?id=com.applay.overlay) を使用
![Widget](./MeterOverlayWidget.jpg)

## リポジトリへのリンク
* [WebSocketGaugeServer](https://sugiuraii.github.io/WebSocketGaugeServer/)
	* Read the sensor information from ECU or control unit (via serial port) and broadcast the information via websocket.
* [WebSocketGaugeClientNeo](https://sugiuraii.github.io/WebSocketGaugeClientNeo/)
	* HTML5 (+WebGL or canvas) based gauge viewer (client) application.
* [ArduinoPulseSensorGeneratorReader](https://sugiuraii.github.io/ArduinoPulseSensorGeneratorReader/)
	* Arduino skethes to read speed/rpm pulse and boost/temperature voltage.
* [DefiCOM_SSMCOM_Emulator](https://sugiuraii.github.io/DefiCOM_SSMCOM_Emulator/)
	* Emulator for defi-link and Subaru select monitor (SSM). (This is useful for debugging custom gauge client application).

