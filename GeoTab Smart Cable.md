[[On-going Tasks]]
(Re: end customer info)
(Re: Geotab smart cable)

---

[[Stakeholders - Geotab Smart Cable]]

2021-11-18(四) 

Kevin.hsueh 指派 RD 窗口 (`Re: Geotab smart cable`)

Stark 解釋 Geotab Concall 窗口介紹 (`Re: Geotab smart cable`)

Indie 來訪
- `ryan.su@indiemicro.com` (Director, Application Engineering & Technical Marketing) 
- `eric.lin@indiemicro.com` (Technical Marketing Director) 

我方幾乎所有人都參與：PM、PMD、EE、SW、ME、採購

沒有明確結論

---

2021-11-22 (一)

申請 RFQ0642、召開 Feasibility 會議

目的：
- 1.Potential Geotab Market Share
- 2.Complete Product Line for Existing Customers
- 3.Earn CANbus Reading Market Share
- 4.Become a Total Solution Provider

需求：
- HW) All OBDⅡ pins are available
- HW) Different "Connector + Cable bodies" for Different Cases
- HW) Interface for Panic Button (OBD Side)
- HW) Clean Installation Design
- SW) Fully Compatible with EVO/Gemini/Sprint/Tablet
- SW) An environment for Geotab to install their software
- SW) Friendly SDK for 3rd Party Software Providers to develop their own software
- SW) Upgrade Firmware via Local / OTA
- SW) 產測程式 for QC

Milestone:
- Rough price evaluation with ME and EE: Dec. 10th 
- ID: Dec. 10th 
- Sales market research and input (Lifecycle, GP, quantity, customer intention): start from Oct 4th until Dec. 24th  
- DVT: Mar. 31st , 2022
- MP: Jul. 29th , 2022

錄音檔
PPT檔，[連結](https://docs.google.com/presentation/d/1kTxEE9ZZdIr1WkKOGnNbc5hw0OElkF_w/edit?usp=sharing&ouid=112782493369308983971&rtpof=true&sd=true) 

---

2021-11-24 (三)

取到樣品2個，含1個模擬器。提供給 Roy，告知其它人 
Ryan 來現場為 RD 解說 

---

2021-11-25 (四)

Indie Ryan 來訪教 RD 怎麼架環境 

---

2021-11-30 (二)

詢問 Denny.cm 後，大概了解了一下SW架構是怎回事

看來是我們 SW 自己就有辦法直接定義開發內容讓 Geotab 知道，有要調整再調整，而 SW 開發過程中有什麼問題就直接詢問 Indie 的 Ryan ，他們已經私下有聯繫。對 Geotab 來說，就是看我們的開發內容和時程，有意見就提出，沒有就看著我們做到某個階段，接手開發即可

---

[[2021-12-01 (三)]]

SURVEY 板子大小優化 → EE

SURVEY 是否留一段線，留多長 → PM, Geotab 
- #elliotyou google 一下，以及詢問 #grace, Terry

Pin Definition → PM, Geotab 
- #elliotyou 與 Geotab 開會 double check 後再回覆給 #ericeh 和 #jeffFang

EE/ME Design for ID → EE, 12/10 #jeffFang #flame

Rough EE cost → EE, 12/10 #jeffFang 

Geotab Verification Method → PM 
- #elliotyou 告知 Geotab 我們會開發 SDK 若他們要用自己的方式，還得再討論要怎麼做產測程式。那會是另一套

MiTAC SDK Schedule → SW, 12/10

#elliotyou 要再發一封 meeting minute 出來 

#elliotyou 與 Stark double check 晚上 Geotab 會議要問的問題 


---

問 Geotab:
- Possible to transmit data via RS232?
- Double check OBDⅡ pin definition
- Comments about "connector + PCB" ? 
- Develop after our SDK ?

Future Items:
- OBDⅡ 轉 J1939 的轉接頭


