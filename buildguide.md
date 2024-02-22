# TL Split Keyboard 16mm Rev1ビルドガイド

TL Split Keyboard 16mm Rev1は、TRON配列のキーボードです。
TRONキーボードMサイズの16mmピッチを、Cherry MXキーで実現しています。

## 説明
TL Split Keyboard 16mm Rev1は、PCBが左右違います。4.7kΩ抵抗（R1,R2）がある方が左です。
基本的に、左側にUSBケーブルを接続するようにしています。

PCBには、表面と裏面があります。"TL Split Keyboard"と記載がある方が、表面です。

## 組み立て
### PCBへパーツ半田付け

- ダイオードを、左右PCB裏面に36カ所実装します。

ダイオードを、左右PCB裏面に実装します。ダイオードは極性があるので、カソード（黒い方）をシルク印刷で線が入っている方（かつKと書かれて、穴が四角の方）になるよう、左右それぞれ36カ所半田付けしていきます。

- 4.7kΩ抵抗を左側PCB表面に2カ所実装します。

4.7kΩ抵抗を、左側PCB表面のみに実装します。極性は無いので、どちらでもかまいません。

- リセットスイッチを、左右PCB裏面に実装します。

リセットスイッチを、左右PCB裏面に実装します。左右PCBそれぞれに1カ所ずつリセットスイッチ位置があるので、半田付けしてください。

※裏面にシルク印刷されています。

- TRRSジャックを、左右PCB裏面に実装します。

TRRSジャックを、左右PCB裏面に実装します。左右PCBに、それぞれ半田付けしてください。

※裏面にシルク印刷されています。

### Pro Microへコンスルー半田付け

遊舎工房で購入すれば、コンスルー付きが買えます。

PCBから外した状態で、部品（USBコネクタなど）が実装されている面にコンスルーを載せて、半田付けします。

できたら、左右PCBの裏面にはめ込みます。基板の外側（左側は左、右側は右）にUSBコネクタが来るようにはめます。

### CherryMX キースイッチ半田付け

アクリルのトッププレートとPCBの間にスペーサー(3mm)をはさみ、左右それぞれ6カ所ネジ止めします。ねじ頭が上側に来るようにして、PCBの下にはスペーサー(10mm)で止めてください。
キースイッチをアクリルトッププレートの上からアクリル・PCBにはめ込み、固定します。ここでキーが浮かないよう、しっかりトッププレートにはめ込んで、半田付けしてください。

CherryMXキースイッチは、親指扇形部分以外の72カ所半田付けします。

※注意点:親指キー部分は、キースイッチによっては干渉してしまう場合があります。その場合、干渉するキーの出っ張り部分をニッパ等で切り落としてください。

## ProMicroにファームウェア書き込み
[QMK Toolbox](https://github.com/qmk/qmk_toolbox) で、ファームウェア（hexファイル）をProMicroに書き込む必要があります。

[QMK Toolbox](https://github.com/qmk/qmk_toolbox) のインストール・使い方については、サリチル酸さんが書かれた[（初心者編）自作キーボードにファームウェアを書き込む](https://salicylic-acid3.hatenablog.com/entry/qmk-toolbox) が分かりやすいです。

TL Split Keyboard 18mmmと16mmはファームウェアが共通なので、 [tlsplit18_default.hex](https://github.com/satromi/tlsplit18_rev1/blob/master/tlsplit18_default.hex) をダウンロードしてQMK Toolboxで書き込みます。

ファームウェアは、左右のProMicroそれぞれに書き込む必要があります。

他のキーマップに変更したい場合は、VIA対応ファームウェアも準備しています。[tlsplit18_via.hex](https://github.com/satromi/tlsplit18_rev1/blob/master/tlsplit18_via.hex) をダウンロードして、QMK Toolboxで書き込みます。

VIA対応ファームウェアの場合、Webサイトからキーマップを変更できる [REMAP for QMK Firmware 0.18.17 or lower](https://qmk018.remap-keys.app/)  も利用できます。
[REMAP for QMK Firmware 0.18.17 or lowerのTL Split Keyboardページ](https://qmk018.remap-keys.app/catalog/AqZy7RsTgu0kxObJxxYr)  から書き換えてみてください。

## 動作確認

左右のキーボードをTRRSケーブルで繋いだら、USBケーブルでPCと接続し、動作確認してください。
