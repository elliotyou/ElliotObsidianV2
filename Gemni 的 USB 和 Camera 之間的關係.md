
AIT, A50, i10, i20 ... 這些術語都是同一類。之前我們因為某個客人，特別跟這間AIT整合過，AIT是公司名稱不是格式名稱。AIT給的 usb camera 是已經壓縮好 H264，對 Gemni 來說只要下 command 去要大小 stream 就可以，不會吃到太多 Gemini 的效能

而之前拿凱木金的樣品給 Nell測，她說會不行也是因為這個原因 (`RE: TVI/USB Rear Camera Verification`)，因為 凱木金 的樣品是一般市面的 usb camera，是傳 RAW DATA ([UVC](https://zh.wikipedia.org/wiki/USB%E8%A6%96%E9%A0%BB%E9%A1%9E%E5%88%A5))，資料沒有被 encode 過，Gemni 那邊收到後要自己再去 encode 並壓出不同的 stream ，會影響到 Gemni 既有的效能。

當前 Gemni 450 的效能就是 1080P\*60FPS。因為有前後鏡，加上大小圖，所以拆成  
1. 前大 (720P \* 15FPS)
1. 前小 (640P \* 15FPS)
1. 後大 (720P \* 15FPS)
1. 後小 (640P \* 15FPS)

- [ ] Nell 那邊之前也曾經測過 450 接 3 支 camera 下的極限，可索取 REPORT #paulchen 
