[[GeoTab Smart Cable]]

---

```javascript

const thought = Stark() //我來之前就被討論過想法
const feasibility = Stark(thought) //我來之前就已經有被討論過可行
const Approvement = Stark() //2021/11/18 Stark 請廠商來，請我也拉一堆人來，這就確定是玩真的了
const MemberList_v1 = RDC3(Approvement) //2021/11/19 Kevin.hsueh 指派了RD窗口
const RFQ_Code = PM(Approvement) //2021/11/19 申請到 RFQ Code
const Purpose = PM(Approvement) //2021/11/21 與 Stark Sync 後得到初版
const Requirement_v1 = PM(Approvement) //2021/11/21 與 Stark Sync 後得到初版
const RFQ Document = PM(Purpose, Requirement_v1, RFQ_Code) //2021/11/22 召開 RFQ 會議
const PRD_v1 = PM(Requirement_v1) //2021/11/29 EE Eric 協助下製作
const PRD_v2 = PM(Geotab comment) //2021/12/4 考量 Geotab 的 Protocol以後
const PRD_v3 = PM(PRD_v2) //2021/12/7 同步 EE 後續對 pin out 的設計以後
const MemberList_v2 = PM() //2021/12/8 詢問RF/EMI/ID/Safety/PJE/PMP/DQE以後
const EE_Design = EE(PRD_v3) //2021/12/9 EE 將初步的設計稿完成

_DXF = ME(EE_Design) //
_3D = ME(EE_Design) //
Placement_Result = EE(_DXF) //
ID_Design_v1 = ID(_3D) //
EE_Cost_v1 = EE(PRD_v3)
SW_Schedule_v1 = SW() //
SW_WBS_v1 = SW() //
Key_Part_Availability_v1 = EE(PRD_v3)
Sample_Prediction_v1 = PJE(MemberList_v2) //


Tooling_Cost
Safety_Cost
Sample_Cost
RF_EMI_Cost
MKL_COST
HUMAN_COST

NRE_Expense_v1 



```