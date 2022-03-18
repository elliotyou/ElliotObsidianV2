---
date: 2022-03-18
tags: log/project/RFQ0644 
---

2022-03-15:
- EE Jerry 說不一定要 EVT 又 DVT
- 確實有可能 DVT 就好，但重點還是要看 EVT 後結果如何
- 如果順利，那的確有可能 1 段就好而不用 2 段

2020-03-15:
- 詢問 Schedule 以後才知道原來 Sensor Driver 要開發 3 個月，然後才可以開發 IQ，接著才有 DQE，排一排會到 2022-10-08
- [Schedule Link](https://app.gantt.io/9004253a-323a-4a8e-85c2-d679f8311e73/gantt/b95600db-5ce2-4fd9-b72c-6c934c2a6a29)

2022-03-16:
- Stark 討論 Schedule
- 8328P 和 F32 不應該從頭開始 tune
- 更不可能 IQ 一個月就好
- 就算真的 F32 的 sensor driver 要 3 個月，那 IQ 只會更久
- 但這不合理，因為 F32 不是全新的東西，BBC 也很熟
- 頂多 F32 和 8328P 沒點亮過，但這是 AIT 推薦的，AIT 應該是可以協助這一段，可能可以參考 F22 ？

2022-03-16 會議記錄: 
1. 此 In-cabin 除了使用在 EVO 上以外，既有的 Gemini 也會需要，In-cabin 優先度遠高於DMS
2. In-cabin 的Lens 改為與蕭邦同顆，因此會有2個 sensor board，我會再補PRD出來
3. 此專案的ROI還是in-cabin + DMS 一起估，而Schedule 拆成 in-cabin和 DMS 分開，我會再補一份出來
4. 安排以i10/i20手改的方式讓Sensor Driver 提前開始開發，我會再與各單位確認怎麼安排

2022-03-18:
- Peggy 再次拉會議請各 RD 再想之後，就找到了一個專案 Blossm 是用過 F32 + 8328P，所以 sensor driver 那段時間可以省掉，只差硬體要先幫他們生 1 台蕭邦 Lens + Blossm main board + Blossm sensor board + i10機構，這樣 SW 就可以先開發，時程就可以排到 7 月底

