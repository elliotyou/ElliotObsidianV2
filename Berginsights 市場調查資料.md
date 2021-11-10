[[MDT新手筆記]]

---

參考資料
[[BergInsights_VideoTelematics.pdf]]

---

[[2021-11-10 (三)]]

Summary:
 Video 是趨勢
 品牌: 
 領導品牌: Streamax, Lytx, Samsara
 其它品牌: SmartDrive Systems, KeepTruckin, SmartWitness
 Nauto, Trimble, SureCam, VisionTrack, Netradyne, Seeing Machines, CameraMatics, LightMetrics

CH1
1.1 
Video方案已經是主流，不管是consumer還是commercial用車，都會有 video 的設備在車上，以 consumer 來說，最基本就是 dashcam 行車紀錄器自保，進階一點就是拍車子的週邊，目的也是自保。而 commercial 有管理目的，則是會再進一步做到 ADAS 和 DMS，CDR 方案 either 是直接 standalone使用，or 本來用 tracker 擴充到 video
1.1.1
Level1: single cam, no integration, no SIM
Level2: single cam + SIM + backend
Level3: multiple cam + SIM + backend + AI
HW層面，基本組成: GSM, GPS, G-sensor, camera, speaker, microphone, secondary camera, dual-facing camera, DVR (USB flash, SD , SSD)
Camera型態: road-facing, cabin-facing, side-facing, rear-facing. 360-degree.
event-triggered video clips (pre-alarm)
on-demand retrieval of any recorded videos
1.1.2
 FM (fleet management) 應用場景 (威潤產品所COVER)
 data logging, satellite positioning, data communications
 數十年前就有的需求
被量產到爛掉，隨處可見，便宜
關鍵的考量: 
- 與車子的整合，車上的資料，包含CAN， 各種配件去和各種車相接的可能性
- GPS:
- GSM
- Platform

Video Telematics 的主目的和上述的場景有點不同，反而不是他們的剛需，而是進階延伸的功能之一

1.2
FM會裝CAM的主要理由是 isurance 和 DMS
即便是最基本的 dashcam 也能起到效果，就像傳統的 CCTV 用法一樣，遇到問題我來回放究責
厲害一點的方案，可以綜合考量車上數據，還有其它視角的CAM，包含 in-cabin 的 DMS 行為分析，road-facing 的CAM來判斷是不是有車道偏移…等
為了節省資源，會是 BY EVENT 上傳VIDEO，而不是全時錄影然後全部都上傳
有了VIDEO 也可以再做到 ADAS 的效果，即時提醒司機自己沒注意到的狀況，caoching

1.2.1
DMS 的應用可以減少一些不必要的浪費
相較於事後的究責，更可以即使的調整預防意外發生

1.3 
Business models 可以是垂直整合，從 HW, SW, brand, project, 到系統整合
比較大的企業會走 Direct Sales ，買high-end產品
小客人則是 inderect sales, 透過中間商轉售
provider 拓展不同區的生意就要靠 resellers
也會有客人談獨家
價格差異很大，要看有沒有DVR，以及CH數
現在收費的主流是靠 subscribe 服務，SAAS，甚至可以HW不收錢，全靠後續的 monthly fee 回收
一開始的硬體費用大概在USD 500~1000，每月的收費是落在USD20~50
透過 mothly fee 的做法，價格比較不好直接比較，有的人可能只 subscribe 某些部分的後台功能
HW provider 會有多條線在賣，有可能賣給中盤，也有可能直接賣給 END USER，或是SI、或OEM
現在不太會有純HW供應者，通常他們自己也會有SW方案和VIDEO方案，不過會是比較基本款，如果跟那些專門在做 VIDEO 後台的人相比的話。所以通常也都是FREE提供給HW買家
 
2.1
FM主要市場在北美和UK

2.1.1
這個相關市場中有不同的玩家，有的是以video為主力專賣商用車，或是像威潤這種以車機為主力附加video功能，或是像陞泰那種以DVR Camera為主力往車用市場切
Streamax 是HW的領導品牌
Lytx 則是擁有 video 服務訂閱數最高，超過60萬
Samsara 則是厲害在 deploy 大量CAM給他們的訂閱用戶
 