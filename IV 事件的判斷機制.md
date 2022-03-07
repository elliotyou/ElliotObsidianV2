

我們自己 IV 方案的事件類型總共有這些：

ADAS
- Front collision
- Tailgating
- Lane departure
- Stop & go

DMS
- Distracted
- Sleepy
- Yawning
- Cellphone

底下一一說明

Front Collison
- 有分 day mode / night mode 。速度是主要的判定條件。 目前APP是設定 30km/h 以上開始判定。至於 30km/h 以後，IV 是用畫面上怎樣的機制來判定是否觸發 Front Collison，這部分要請RD詢問IV細節才知道，這要問是可以

Tailgating
- 跟 Front Collision 一樣有分 day / night。目前 APP 是設定速度 60km/h 以上開始判定。同理，他判定的邏輯演算法細節要問IV才知道

Lane Departure
- 跟上述2個相同，但是沒有分 day / night，時速 30km/h 以上開始判。也是一樣，演算法細節要問 IV 才知道

Stop & Go
- 就有點不同，他是時速為0才有可能啟動，沒有 day / night 之分，只有這個功能的 on/off 之分而已

DMS 的所有事件都不看速度，隨時都有可能啟用，4 個不同的事件演算法細節也要問 IV 才知道

以上所有的事件都可以 offline 在 CDR 裝置中判斷，不需要靠網路 (Edge Computing)，有植入 IV 的演算法在 APP 裡