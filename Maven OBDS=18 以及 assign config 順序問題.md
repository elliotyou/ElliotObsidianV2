From: [[2021-10-21 (四)]]

---


From: Elliot [mailto:elliot@atrack.com.tw] 
Sent: Thursday, October 21, 2021 5:43 PM
Subject: RE: Maven issues

Hi Brian, 

$OBDS=18 Timeout 問題:

AT$OBDS=18 ”有機會” 造成ADM在執行 task時timeout，但並非”總是” 如此

今天與Otis確認過如果單純將ADM上的等待時間改成20秒的話，影響還蠻大的，很多程序都會跟著拉長
例如: `AT$INFO? AT$ADMS=? AT$OEMD=?` 的這個問題就會先等個20秒 (死等在那不做事的那種)，所以真的要改的話只能是針對性的改(在特定程序才等20秒)。
這部分要再與 Otis 確認

而如果我們保持原狀不改任何東西，其實對客人的影響並沒有很大，因為Failed task 在下一次機器連上 ADM 後再執行時就會成功 (因為第2次上來時 $OBDS 已經18)，而 ADM 本來也就會自動 retry 。因此對Maven來說他仍然是「assign task一次，然後等待完成」而已，並不會多做什麼動作。頂多在「ADM執行第2次以前」會看到任務是Failed狀態而已

ADM FW task 和 Configuration task 順序問題:

如果 pending task 中同時存在 configuration task 和 firmware task，車機和ADM之間的行為如下：
執行 firmware task → send $FOTA → 車機斷線 → 車機再次連回ADM → 

此時分成兩種case，
 - 如果ADM確認版本有更新 → 發現還有pending configuration task → 執行 configuration task → 兩個task都完成 (End)
 - 如果 ADM 看到版本沒更新 → 發現還有pending configuration task → 仍先執行 configuration task → 再次執行firmware task → send $FOTA → 車機斷線 → … (啟動 retry 機制)

即使Maven 「先assign firmware 再 assign configuration」也無法 100% 確認一定是先更新 firmware 後才做 configuration.
 - 如果首次的firmware upgrade 是順利的，那就是他要的順序沒錯
 - 但如果首次的firmware upgrade是失敗的，那就不會是他要的順序

結論：如果要確保 configuration 必在 firmware upgrade 後執行，目前Maven只能照下面的方式操作：
1.  挑出所有待執行的IMEI，先存成一張表，例如 500個IMEI
2.  ADM上Search 出此 500 台以後，僅 assign firmware 
3.  過一段時間後
4.  再次Search出那500台，透過Export的功能匯出一份 excel 檔
5.  從該 excel檔中，filter 出firmware版本已是新版的機器，假設200台
6.  複製貼上此200台，在ADM上search 並 assign configuration
7.  將 excel 檔中的此 200 台移除
8.  再過一段時間
9.  ADM Search 剩下的 300台，filter出firmware版本是新的機器…反覆相同動作

若果他們嫌麻煩需要ADM可支援此功能的話，就不是短時間內可以生出來的功能了，這要再找Otis 和 John 討論
