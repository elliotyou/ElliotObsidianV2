[[On-going Tasks]]
(Re: end customer info)
(Re: Geotab smart cable)

---

[[Stakeholders - Geotab Smart Cable]]

[[Mail Log - Geotab Smart Cable]]

[[PMP - Geotab Smart Cable]]

2021-11-22 (一) 申請 RFQ0642、召開 Feasibility 會議
`"d:\Downloads\MiTAC\Documents\Geotab Smart Cable\SmartCable_Feasibility_20211122.PPTX" `

2021-11-25 (四) Indie Ryan 來訪教 RD 怎麼架環境 

2021-11-30 (二) 詢問 Denny.cm 後，大概了解了一下SW架構是怎回事
- 看來是我們 SW 自己就有辦法直接定義開發內容讓 Geotab 知道，有要調整再調整，而 SW 開發過程中有什麼問題就直接詢問 Indie 的 Ryan ，他們已經私下有聯繫。對 Geotab 來說，就是看我們的開發內容和時程，有意見就提出，沒有就看著我們做到某個階段，接手開發即可

Geotab Verification Method
- 不需要徵求 Geotab 意見, 由我們主導。我們要把預計做的 SDK 項目展開，還有 SCHEDULE，讓他們知道即可。如果他們有需要加，再另外討論。若沒有，就只照我們的步調

2021-12-02 (四) #elliotyou 10:11 Stark is explaning to MAU in his way

---

**SURVEY 是否留一段線，留多長** → PM, Geotab 
- #elliotyou google 一下，以及詢問 #grace, Terry

**Pin Definition** 
- #elliotyou 所有 protocol 的那個問題直接問 Geotab 的 Jason。跟 #stark 要一下那個 GEOTAB 給過的資料

**Geotab 會議，與會者之間的關係**
- #elliotyou 會議記錄要記一下，主要是那幾個人之間的關係


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

2021-12-01 (三)

SURVEY 板子大小優化 → EE

SURVEY 是否留一段線，留多長 → PM, Geotab 
- #elliotyou google 一下，以及詢問 #grace, Terry

Pin Definition → PM 
- #elliotyou 與 Geotab 開會 double check 後再回覆給 #ericeh 和 #jeffFang

EE/ME Design for ID → EE, 12/10 #jeffFang #flame

Rough EE cost → EE, 12/10 #jeffFang 

Geotab Verification Method → PM 
- 與 Stark 討論後，不需要徵求他們的意見，我們自己主導就好。我們就照自己的步調，把會做的項目列出來給他們參考，若他們覺得有不足之處，再來加。至於到時候怎麼 verify 出給他的東西都是灌好無誤，這是我們的功課，不是他們的

MiTAC SDK Schedule → SW, 12/10

發封 meeting minute 出來 

與 Stark double check 晚上 Geotab 會議要問的問題。
- Geotab 就只是等著看著我們硬體做好他灌軟體這樣而已。就把它想成我們是做電話和佈電話線的人，他們只是到時候要來講話的用戶。我們不會問他 pin definition ，我們只會問他需要用到哪些 protocol ，然後我們自己知道哪幾 pin 要留著這樣，如果我們還要他定義 pin define 我們才能做的話顯得有點不專業。
- 接頭和PCB 之類要不要留一段線，也跟他們無關，我們自己決定就好，他們也不一定熟悉這部分，他們就只是需要有人幫他做個載體

晚上 22:00 和 Geotab, Indie Concall

#elliotyou 跟 #roy 和 #dennyCm 確認一下他們要買的是哪個模擬器，把連結 share 出來給他們

---

Future Items:
- OBDⅡ 轉 J1939 的轉接頭


