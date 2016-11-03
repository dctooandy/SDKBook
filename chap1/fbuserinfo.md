#8.Facebook 使用者名單撈取介接
###8.1 取得使用者基本資訊(FB_getUserInfo)流程說明
“FB_getUserInfo”(FB 使用者基本資訊撈取)可取得使用 Facebook 帳號登入 的使用者，與其 FB 好友中已授權此 APP 的個人基本資訊。

####8.1.1 參數定義

|功能名稱|FB_getUserInfo|
|:--:|--|
|功能描述|取得 FB 使用者基本資訊|
|回傳格式|NSDictionary(需實作 FB_getUserInfoComplete)|

<table border="1">
<tr>
<td rowspan="2">request<br>(傳入參數)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br> 必要</td>
<td>類型</td>
</tr>
<tr>
<td>ids</td>
<td>好友 id，如傳 nil、空陣列、陣列元素為空字串，<br>則取得自己(me)的基本資訊</td>
<td>Y</td>
<td>NSString<br>NSArray</td>
</tr>
</table>

<table>
<tr>
<td rowspan="5">response<br>(回傳結構)</td>
<td>參數</td>
<td>說明</td>
<td>繼承<br>欄位</td>
<td>類型</td>
</tr>
<tr>
<td>valid</td>
<td>成功與否</td>
<td>根</td>
<td>[NSNumber by BOOL]<br>NSArray</td>
</tr>
<tr>
<td>msgid</td>
<td>回傳之訊息編號，<br>請參考附錄 A. Message</td>
<td>根</td>
<td>[NSNumber by Integer]<br>NSArray</td>
</tr>
<tr>
<td>msg</td>
<td>回傳之訊息內容，<br>請參考附錄 A. Message</td>
<td>根</td>
<td>NSString<br>NSArray</td>
</tr>
<tr>
<td>info</td>
<td>回傳之基本資訊，為 Facebook 回傳的<br>JSON 資訊，通常轉成 NSDictionary，包<br>含 id 、 name 、 picture 、 first_name 、<br>last_name 、 gender 、 locale 、 link 、<br>updated_time，若某筆資訊取得失敗，其<br>對應的 info 為空字串</td>
<td>根</td>
<td>id<br>NSArray</td>
</tr>
</table>

####8.1.2 程式實作
執行取得 FB 使用者基本資訊範例

>// 取得 FB 使用者基本資訊<br>
>[[LoginView sharedApplication] FB_getUserInfo:NSArray];

執行後回傳參數範例

範例 :<br>
{“valid”:[1, 0],<br>
“msgid”:[200, 998],<br>
“msg”:[Success, not authorize],<br>
“info”:[{JSON}, “”]}

###8.2 取得已授權好友名單(FB_getAuthFndList)流程說明
“FB_getAuthFndList”(已授權好友名單撈取)可取得使用 Facebook 帳號登入
的使用者 FB id，與其 FB 好友中已授權此 APP 的 id、name、pictureUrl。

####8.2.1 參數定義
|功能名稱|FB_getAuthFndList|
|:--:|--|
|功能描述|取得使用者 FB id 與已授權好友的 id、name、pictureUrl|
|回傳格式|NSDictionary(需實作 FB_getAuthFndListComplete)|

<table border="1">
<tr>
<td rowspan="2">request<br>(傳入參數)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br> 必要</td>
<td>類型</td>
</tr>
<tr>
<td>uid</td>
<td>使用者的 iSGame 平台 id</td>
<td>Y</td>
<td>NSString</td>
</tr>
</table>

<table>
<tr>
<td rowspan="5">response<br>(回傳結構)</td>
<td>參數</td>
<td>說明</td>
<td>繼承<br>欄位</td>
<td>類型</td>
</tr>
<tr>
<td>valid</td>
<td>成功與否</td>
<td>根</td>
<td>[NSNumber by BOOL]<br>NSArray</td>
</tr>
<tr>
<td>msgid</td>
<td>回傳之訊息編號，<br>請參考附錄 A. Message</td>
<td>根</td>
<td>[NSNumber by Integer]<br>NSArray</td>
</tr>
<tr>
<td>msg</td>
<td>回傳之訊息內容，<br>請參考附錄 A. Message</td>
<td>根</td>
<td>NSString<br>NSArray</td>
</tr>
<tr>
<td>info</td>
<td>回傳之基本資訊，為 Facebook 回傳的<br>JSON 資訊，通常轉成 NSDictionary，包<br>含 id 、 name 、 picture 、 first_name 、<br>last_name 、 gender 、 locale 、 link 、<br>updated_time，若某筆資訊取得失敗，其<br>對應的 info 為空字串</td>
<td>根</td>
<td>id<br>NSArray</td>
</tr>
</table>