

當你去 google 「obd2 pin definition」，會看到類似下方的圖和定義

<a href="https://imgur.com/MMagcU7"><img src="https://i.imgur.com/MMagcU7.png" title="source: imgur.com" width="300px"/></a>

|Pin Number|Pin Name|Description|
|---|---|----|
|1,3,8,9,11,12,13|Blank|These pins are not standard and are vendor specific. It is also not required for normal communication/interfacing|
|2|SAE J1850 Bus+|This protocol uses Variable Pulse Width and is normally used by GM vehicles. This is the Bus positive pin of the protocol.|
|10|SAE J1850 Bus-|This protocol uses Variable Pulse Width and is normally used by GM vehicles. This is the Bus negative pin of the protocol.|
|4,5|Ground|Ground of complete system of the Car including chassis|
|6|ISO15765-4 CAN High|It follows 2-wire CAN protocol at 1Mbps speed. This is the CAN high Pin|
|14|ISO15765-4 CAN Low|It follows 2-wire CAN protocol at 1Mbps speed. This is the CAN low Pin|
|7|ISO 9141 – K Line|It follows asynchronous serial communication protocol, this pin is the K line|
|8|ISO 9141 – L Line|It follows asynchronous serial communication protocol, this pin is the L line|

Ericeh.huang 補充：
- OBDⅡ 沒有特別定義 3 和 11 ，不過通常有第 2 組 CAN 的車廠，都會把它做在 3 和 11。所以 Geotab Smart Cable 再最初要設計的時候，就要留好 3 和 11
- 其中 2 和 10 (SAE J1850 BUS ±) 雖然看起來只有 1 組，但其實它有 2 個不同的 protocol 同時在跑
- 1, 9 沒有在標準裡，但確留在 PIN 中，是因為曾經有很古老的，類似 OBD 的 protocol 做在那上面，但後來沒有成為主流，所以留著，又沒寫在這