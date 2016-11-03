#9.Facebook 分享功能介接
###9.1 邀請好友(FB_inviteViaFriendList)流程說明
“FB_inviteViaFriendList”可讓使用者向 Facebook 好友發送 APP 邀請;<br>
發送成功可取得被邀請者的 FB id。貴方若想使用此功能，應在 APP 中加入串接本功能的按鈕UI。

####9.1.1 參數定義

|功能名稱|FB_inviteViaFriendList|
|:--:|--|
|功能描述|向 Facebook 好友發送 APP 邀請|
|回傳格式|NSDictionary(需實作 FB_sharingComplete)|

<table>
<tr>
<td rowspan="4">request<br>(傳入參數)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br>必要</td>
<td>類型</td>
</tr>
<tr>
<td>uid</td>
<td>使用者的 iSGame 平台 id</td>
<td>Y</td>
<td>NSString</td>
</tr>
<tr>
<td>message</td>
<td>發送邀請時所顯示的訊息文字<br>(PC 用戶才看得到)</td>
<td>Y</td>
<td>NSString</td>
</tr>
<tr>
<td>autoSelect</td>
<td>開啟/關閉自動選擇 FB 好友功能<br>*自動選擇僅會發送給尚未授權的朋友</td>
<td>Y</td>
<td>BOOL</td>
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
<td>NSNumber</td>
</tr>
<tr>
<td>msg</td>
<td>失敗或取消的訊息。若成功則回傳空值</td>
<td>根</td>
<td>NSString</td>
</tr>
<tr>
<td>data</td>
<td>被邀請者的 FB id。若無則回傳空陣列</td>
<td>根</td>
<td>NSArray</td>
</tr>
<tr>
<td>event</td>
<td>執行分享的函式名(如此功能名稱)</td>
<td>根</td>
<td>NSString</td>
</tr>
</table>

####9.1.2 程式實作
執行 Facebook 發送 APP 邀請範例
>執行 Facebook 發送 APP 邀請範例<br>
>[[LoginView sharedApplication] FB_inviteViaFriendList:@"xxx"
sendMessage:@"xxx" autoSelect:NO];

執行後回傳參數範例

- 範例 1:<br>
{<br>
“valid”:1, <br>
“msg”:“”, <br>
“data”:[1458495727776393, 1458495727776394],<br> “event”:”FB_inviteViaFriendList”<br>
}

###9.2 邀請好友(FB_sendInvitationWithToken)流程說明
“FB_sendInvitationWithToken”可讓使用者使用 Invitable token 向 Facebook 好友發送 APP 邀請;發送成功可取得被邀請者的 FB id。貴方若想使用此功能， 應在 APP 中加入串接本功能的按鈕 UI。

####9.2.1 參數定義
|功能名稱|FB_sendInvitationWithToken|
|:--:|--|
|功能描述|使用 Invitable token 向 Facebook 好友發送 APP 邀請|
|回傳格式|NSDictionary(需實作 FB_sharingComplete)|

<table>
<tr>
<td rowspan="3">request<br>(傳入參數)</td>
<td>參數</td>
<td>說明</td>
<td>是否<br>必要</td>
<td>類型</td>
</tr>
<tr>
<td>uid</td>
<td>使用者的 iSGame 平台 id</td>
<td>Y</td>
<td>NSString</td>
</tr>
<tr>
<td>message</td>
<td>發送邀請時所顯示的訊息文字<br>(PC 用戶才看得到)</td>
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
<td>NSNumber</td>
</tr>
<tr>
<td>msg</td>
<td>失敗或取消的訊息。若成功則回傳空值</td>
<td>根</td>
<td>NSString</td>
</tr>
<tr>
<td>data</td>
<td>被邀請者的 FB id。若無則回傳空陣列</td>
<td>根</td>
<td>NSArray</td>
</tr>
<tr>
<td>event</td>
<td>執行分享的函式名(如此功能名稱)</td>
<td>根</td>
<td>NSString</td>
</tr>
</table>