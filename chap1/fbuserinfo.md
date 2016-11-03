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
