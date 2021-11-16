[[MitTAC Solutions]]

---

要先得到 CDR 的 wifi mac 以後，換到一個 license key

我們的 app 才能由該 License key 取得 IV 的 Service

要知道 app 是否啟用成功，可以去 Vysor 裡打開 Mio App 看 Inward view 是否有下方的功能

若確定有啟用，路測的時候，

DMS 的部分，下方 4 個功能符合的時候會自動觸發 Event

ADAS 的部分，會有 audio caoching，項目並沒有秀在 screen 上，包含: 
- Lane Departure
- Front Collision
- Tailgating

ADAS 需要 Calibration 才能啟作用，而 Calibration 的條件是: 
- 有足夠的 GPS 訊號
- 速度超過 60 km/hr
- 前視野有夠大的面積，露出清楚分隔線條