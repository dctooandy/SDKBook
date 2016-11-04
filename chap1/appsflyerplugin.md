#10.AppsFlyer 介接

###10.1 寄送追蹤事件(SendAFTrackEvent)流程說明

“SendAFTrackEvent”(寄送追蹤事件)可以追蹤 AppsFlyer 的 in-app events。 建議只追蹤有收益的事件，且若只需要觀察玩家轉換為 Pay user 的比率，則可 以不傳入金額。

<font color="red">※請於第一次登入(非 relogin)時，並確定已執行 SaveGameInfo 後執行 af_login 的 AppsFlyer event。</font>

####10.1.1 參數定義
|功能名稱|SendAFTrackEvent|
|:--:|--|
|功能描述|追蹤 AppsFlyer 的 in-app events|
|回傳格式|void|

<table>
<tr>
<td rowspan="3">request<br>(傳入參數)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br>必要</td>
<td>類型</td>
</tr>
<tr>
<td>name</td>
<td>自定義或 AppsFlyer 提供的 event<br>name，請參考<a href="https://support.appsflyer.com/hc/en-us/articles/207577713">這裡</a></td>
<td>Y</td>
<td>NSString</td>
</tr>
<tr>
<td>values</td>
<td>自定義或 AppsFlyer 提供的 event<br>values，請參考<a href="https://support.appsflyer.com/hc/en-us/articles/207577713">這裡</a></td>
<td>Y</td>
<td>NSDictionary</td>
</tr>
</table>

####10.1.2 程式實作
執行寄送追蹤事件範例
<span id="SendAFTrackEvent"></span>

>// 追蹤 AppsFlyer 的 in-app events<br>
>[[LoginView sharedApplication] SendAFTrackEvent:@"xxx" values:NSDictionary];

###10.2 取得深層資料(GetAFConversionData)流程說明
“GetAFConversionData”(取得深層資料)可以拿到 AppsFlyer 的 Install Conversion Data。主要屬性值為「media_source」與「campaign」，其餘屬性 請參考[這裡](https://support.appsflyer.com/hc/en-us/articles/207032096-Accessing-AppsFlyer-Attribution-Conversion-Data-from-the-SDK-iOS-Deferred-Deeplinking-)。

####10.2.1 參數定義
|功能名稱|GetAFConversionData|
|:--:|--|
|功能描述|拿到 AppsFlyer 的 Install Conversion Data|
|回傳格式|id|

<table>
<tr>
<td rowspan="2">response<br>(回傳結構)</td>
<td>說明</td>
<td>繼承<br>欄位</td>
<td>類型</td>
</tr>
<tr>
<td>回傳取得的 AppsFlyer Conversion Data，若得到<br>非 NSDictionary 格式即為 error message</td>
<td>根</td>
<td>id</td>
</tr>
</table>

####10.2.2 程式實作
執行取得深層資料範例
<span id="GetAFConversionData"></span>

>// 拿到 AppsFlyer 的 Install Conversion Data<br>
>id data = [[LoginView sharedApplication] GetAFConversionData];

###10.3 設定使用者郵件(SetAFUserEmails)流程說明
“SetAFUserEmails”(設定使用者郵件)可以設定 AppsFlyer 使用者郵件。

####10.3.1 參數定義
|功能名稱|SetAFUserEmails|
|:--:|--|
|功能描述|設定 AppsFlyer 使用者郵件|
|回傳格式|void|

<table>
<tr>
<td rowspan="2">response<br>(回傳結構)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br>必要</td>
<td>類型</td>
</tr>
<tr>
<td>userEmails</td>
<td>AppsFlyer 用戶信箱</td>
<td>Y</td>
<td>NSString<br>NSArray</td>
</tr>
</table>

####10.3.2 程式實作
執行設定 AppsFlyer 使用者郵件範例
>// 設定 AppsFlyer 使用者郵件<br>
>[[LoginView sharedApplication] SetAFUserEmails:NSArray];