#10.AppsFlyer 介接

###10.1 寄送追蹤事件(SendAFTrackEvent)流程說明

“SendAFTrackEvent”(寄送追蹤事件)可以追蹤 AppsFlyer 的 in-app events。 建議只追蹤有收益的事件，且若只需要觀察玩家轉換為 Pay user 的比率，則可 以不傳入金額。

<font color="red">※請於第一次登入(非 relogin)時，並確定已執行 SaveGameInfo 後執行 af_login 的 AppsFlyer event。</font>

####10.1.1 參數定義
|功能名稱|SendAFTrackEvent|
|:--:|--|
|功能描述|追蹤 AppsFlyer 的 in-app events|
|回傳格式|void|
