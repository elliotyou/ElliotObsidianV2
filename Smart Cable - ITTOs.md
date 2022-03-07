const thought = Stark() //我來之前就被討論過想法
const feasibility = Stark(thought) //我來之前就已經有被討論過可行
const Approvement = Stark() //2021/11/18 Stark 請廠商來，請我也拉一堆人來，這就確定是玩真的了
const MemberList_v1 = RDC3(Approvement) //2021/11/19 Kevin.hsueh 指派了RD窗口
const RFQ_Code = PM(Approvement) //2021/11/19 申請到 RFQ Code
const Purpose = PM(Approvement) //2021/11/21 與 Stark Sync 後得到初版
const Requirement_v1 = PM(Approvement) //2021/11/21 與 Stark Sync 後得到初版
const RFQ_Document = PM(Purpose, Requirement_v1, RFQ_Code) //2021/11/22 召開 RFQ 會議
const *MemberList_v2 = PM() //2021/12/8 詢問RF/EMI/ID/Safety/PJE/PMP/DQE以後

================================================================

const PRD_v1 = PM(Requirement_v1) //2021/11/29 EE Eric 協助下製作
const PRD_v2 = PM(PRD_v1, Geotab_comment) //2021/12/4 考量 Geotab 的 Protocol以後
const PRD_v3 = PM(PRD_v2) //2021/12/7 同步 EE 後續對 pin out 的設計以後
const *EE_Design_v1 = EE(PRD_v3) //2021/12/9 EE 將初步的設計稿完成
const _DXF_v1 = ME(EE_Design_v1) // 2021/12/10 ME Ethan.cai 提供
const _3D_v1 = ME(EE_Design_v1) // 2021/12/10 ME Ethan.cai 提供

================================================================

const UnitCost_EE_v1 = EE(EE_Design_v1) //2021/12/16 EE Eric 提供初步成本
const Key_Part_Availability_v1 = EE(PD(EE_Design_v1)) //2021/12/12 EE Eric 根據採購的訊息，告知關鍵物料的缺料狀況
const UnitCost_Casing_v1 = ME(EE_Design_v1) // Flame 得到初步 Casing 報價
const UnitCost_Cable_v1 = ME(EE_Design_v1) // Flame 得到初步 Cable 報價

const *Placement_Result_v1 = EE(_DXF_v1) //2021/12/16 EE Eric 提供，交由 layout team 畫過以後


Sample_Prediction_v1 = PJE(MemberList_v2, Placement_Result_v1) //
NRE_Tooling_v1 = ME(Placement_Result_v1)
Safety_Cost = Safety(Placement_Result_v1, spec, manual)
Sample_Cost = PJE(Sample_Prediction_v1, unit_cost)
RFEMI_Cost = RFEMI(Placement_Result_v1, )

const Requirement_v2 = Geotab(Placement_Result_v1) //2021/12/23 Geotab John 仍堅持 40*55 太大，需要 downsize ，修正需求

const PRD_v4 = PM(Requirement_v2) //2021/12/24 再找 EE Eric 確認最小能塞到多小，得到 40*40 的可行目標。 對應文件 D045
const ME_Cost_v1 = ME(UnitCost_Casing_v1, UnitCost_Cable_v1) // Flame 從廠商得到 cable 報價，Casing 報價
const PMP_Cost_V1 = PMP(PRD_v4, PM_Opinion, EE_Opinion, ME_Opinion, History_Benchmark) // Cindy 從以往數據、各方意見推測生產 1 台的成本
const Material_Cost_v1 = (UnitCost_EE_v1 + ME_Cost_v1) * 1.085 // 材損
const Unit_Cost_v1 = Material_Cost_v1 + PMP_Cost_V1

ID_Design_v1 = ID(_3D_v1) //
SW_Schedule_v1 = SW() //
SW_WBS_v1 = SW() //

MKL_COST
HUMAN_COST

NRE_Expense_v1 
