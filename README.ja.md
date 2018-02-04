# Welcome to sugiuraii.github.io front page.

以下のプロジェクトを公開しています。

## Websocket automotive gauge project.
### 概要
HTML5(canvas or websocket)を利用したグラフィカルな自動車用外付けメータを作成しています。
シリアルポート経由でECUやセンサユニットから情報を集め、websocketでクライントのWebアプリへ配信します。

* 車両情報 (車速、回転数、水温、ブースト etc..) をPCやスマートフォンのWebブラウザで受信、表示.
	* Websocket経由なのでwifi経由での受信も可。
* メーターを表示するクライアントアプリはHTML5ベースなので、HTML5とWebGL(またはcanvas)をサポートするブラウザがあればOSは問わない.
* クライアントWebアプリのソースコードは公開しているので、自分でカスタマイズも可能.
	* Typescirptとpixi.jsを使用.
* サーバー側はC#で記述しているが、monoでの動作確認済みなのでWindowsでもLinuxでも動作可 (下にRaspberry pi用プレインストールイメージを公開中）.

![接続図](./WebsocketGaugeDiagram.png)

### とりあえずRaspberry piで試してみる.
Pre-installed raspbian image is available on [here](https://sugiuraii.github.io/WebSocketGaugeServer/RasobianImageSetup.ja.html).

### メーターをデザインしてみる
こちらのレポジトリを参照ください。 [WebSocketGaugeClientNeo](https://sugiuraii.github.io/WebSocketGaugeClientNeo/).

### デモ動画.
#### Demonstration on car
<iframe width="640" height="360" src="https://www.youtube.com/embed/QCOYLCIrU_s" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Demonstration on development PC
<iframe width="640" height="360" src="https://www.youtube.com/embed/pAk8FpmZctI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### Arduino sensor unit demo.
<iframe width="640" height="360" src="https://www.youtube.com/embed/HvkB07k6gMc" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

#### ELM327 demo (emulated on obdsim)
<iframe width="640" height="360" src="https://www.youtube.com/embed/l_niGjlkpQ4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### リポジトリへのリンク
* [WebSocketGaugeServer](https://sugiuraii.github.io/WebSocketGaugeServer/)
	* Read the sensor information from ECU or control unit (via serial port) and broadcast the information via websocket.
* [WebSocketGaugeClientNeo](https://sugiuraii.github.io/WebSocketGaugeClientNeo/)
	* HTML5 (+WebGL or canvas) based gauge viewer (client) application.
* [ArduinoPulseSensorGeneratorReader](https://sugiuraii.github.io/ArduinoPulseSensorGeneratorReader/)
	* Arduino skethes to read speed/rpm pulse and boost/temperature voltage.
* [DefiCOM_SSMCOM_Emulator](https://sugiuraii.github.io/DefiCOM_SSMCOM_Emulator/)
	* Emulator for defi-link and Subaru select monitor (SSM). (This is useful for debugging custom gauge client application).

