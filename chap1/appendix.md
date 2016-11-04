# 附錄

###附錄 A. Message
| msgid | msg | 備註 |
| :--: | -- | -- |
| 0 | The request is missing a required parameter, includes<br> an invalid parameter value, includes a parameter more<br> than once, or is otherwise malformed. Check the "%s"<br> parameter | 傳遞參數短少 |
| 1 | The client is not authorized to request an access token<br> using this method | 此 client_id 無法使用此方式<br>進行驗證 |
| 2 | The resource owner or authorization server denied the<br> request | 此 user 被拒絕存取/或<br>server 拒絕此請求 |
| 3 | The authorization server does not support obtaining an<br>access token using this method | response_type 錯誤 |
| 4 | The requested scope is invalid, unknown, or<br> malformed. Check the "%s" scope | scope 參數驗證錯誤 |
| 5 | The authorization server encountered an unexpected<br> condition which prevented it from fulfilling the request | 驗證過程意外中止 |
| 6 | The authorization server is currently unable to handle<br> the request due to a temporary overloading or<br> maintenance of the server | oauth server 維護中 |
| 7 | The authorization grant type "%s" is not supported by<br> the authorization server | 不支援的 grant_type |
| 8 | Client authentication failed | client_id 與 redirect_uri 驗<br>證失敗 |
| 9 | The provided authorization grant is invalid, expired,<br> revoked, does not match the redirection URI used in<br> the authorization request, or was issued to another<br> client. Check the "%s" parameter | 授權請求無效/過期/被撤銷 |
| 200 | Success | 成功 |
| 998 | FB message | FB 相關訊息 |
| 999 | Else message | 發生不可預期的錯誤，導致<br>出現非以上訊息時 |


###附錄 B. Third-party SDK

<table>
<tr>
<td>SDK 名稱</td>
<td>版本號</td>
<td>備註</td>
</tr>
<tr>
<td>Facebook SDK</td>
<td>4.6.0 (Graph API 2.4)</td>
<td rowspan="2">此為建構 iSGame SDK 時的版本。貴方<br>實際導入時，選擇相容的版本導入即可。</td>
</tr>
<tr>
<td>AppsFlyer SDK</td>
<td>3.3.2</td>
</tr>
</table>

###附錄 C. Reference

<table>
<tr>
<td>名稱</td>
<td>說明</td>
</tr>
<td colspan="2" align="center">設定</td>
<tr>
<td> <a href="loginandplugin.md#setDelegate">- (void)
setDelegate:NSObject &lt;IsvDelegate&gt;</a> </td>
<td>設定使用 IsvDelegete 的目標</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#setIsLandscape">- (void)
setIsLandscape:BOOL </a></td>
<td>設定 SDK 畫面以橫向(YES)或直向(NO)顯示;預設為 YES</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#setLocalize">- (void)
setLocalize:
NSString</a> </td>
<td>設定 SDK 介面以繁體中文(zh_TW)或英文(en)顯示;預設為 系統語系(非中則英)</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#setLoginKey">- (void)
setLoginKey:
NSString</a></td>
<td>設定登入後取得的 relogin key，第一次登入請傳空值</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#SaveGameInfo">- (void)
SaveGameInfo:
NSDictionary</a> </td>
<td>儲存介接方使用者資訊</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#sharedApplication">+ (id)
sharedApplication</a></td>
<td>新產生或取得已產生過的 LoginView 物件實例</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#redirectUri">- (void)
init:
NSString
redirectUri:
NSString </a></td>
<td>設定 iSGame client_id 和 redirect_uri</td>
</tr>
<td colspan="2" align="center">帳號</td>
<tr>
<td> <a href="loginandplugin.md#startLogin">- (void)
startLogin</a> </td>
<td>產生登入頁面方法</td>
</tr>
<tr>
<td> <a href="loginandplugin.md#startLogout">- (BOOL)
startLogout</a> </td>
<td>請依需求登出，尤其要提醒未綁定玩家，登出會造成資料遺 失</td>
</tr>
<tr>
<td> <a href="accountplugin.md#startBinding">- (void)
startBinding:
NSString</a> </td>
<td>快登綁定方法，參數為登入者的 uid</td>
</tr>
<td colspan="2" align="center">遊戲</td>
<tr>
<td> <a href="customerandreport.md#serviceReport">- (void)
serviceReport:
NSString</a> </td>
<td>產生客服回報頁面方法，參數為登入者的 uid</td>
</tr>
<tr>
<td> <a href="gameactivity.md#gameActivity">- (void)
gameActivity</a> </td>
<td>產生活動頁面方法</td>
</tr>
<tr>
<td> <a href="gamenews.md#gameNews">- (void)
gameNews</a> </td>
<td>產生公告頁面方法</td>
</tr>
<td colspan="2" align="center">社群</td>
<tr>
<td> <a href="fbuserinfo.md#FB_getUserInfo">- (void)
FB_getUserInfo:
NSArray</a> </td>
<td>取得 FB 使用者基本資訊</td>
</tr>
<tr>
<td> <a href="fbuserinfo.md#FB_getAuthFndList">- (void)
FB_getAuthFndList:
NSString</a> </td>
<td>取得使用者 FB id 與已授權好友的 id、name、pictureUrl</td>
</tr>
<tr>
<td> - (void)
FB_fetchInvitableToken:
NSArray </td>
<td>取得使用者 FB id 與未授權好友的 inviteToken、name、 pictureUrl</td>
</tr>
<tr>
<td> - (void)
FB_inviteViaFriendList:
NSString
sendMessage:
NSString
autoSelect:
BOOL </td>
<td>向 Facebook 好友發送 APP 邀請</td>
</tr>
<tr>
<td> - (void)
FB_sendInvitationWithToken:
NSArray
sendMessage:
NSString </td>
<td>使用 Invitable token 向 Facebook 好友發送 APP 邀請</td>
</tr>
<tr>
<td> - (void)
FB_sendStory:
NSString
objectID:
NSString
actionType:
NSString
sendMessage:
NSString </td>
<td>向 Facebook 好友發送客製邀請</td>
</tr>
<tr>
<td> - (void)
FB_autoSharing:
NSString
Link:
NSString
Title:
NSString
picUrl:
NSString
postMessage:
NSString </td>
<td>可在使用者執行 APP 期間，代替於 Facebook 發佈動態</td>
</tr>
<td colspan="2" align="center">分析</td>
<tr>
<td> - (void)
SendAFTrackEvent:
NSString
values:
NSDictionary </td>
<td>追蹤 AppsFlyer 的 in-app events</td>
</tr>
<tr>
<td> - (id)
GetAFConversionData </td>
<td>拿到 AppsFlyer 的 Install Conversion Data</td>
</tr>
<tr>
<td> - (void)
SetAFUserEmails:
NSArray </td>
<td>設定 AppsFlyer 使用者郵件</td>
</tr>
<td colspan="2" align="center">Delegate</td>
<tr>
<td> - (void)
initialCallback </td>
<td>(required)iSGameSDK 初始後</td>
</tr>
<tr>
<td> - (void)
loginComplete:
NSString </td>
<td>(required)接收 iSGameSDK 登入成功後回傳的授權碼 (code)</td>
</tr>
<tr>
<td> - (void)
bindComplete:
BOOL </td>
<td>(optional)接收帳號綁定結果(YES 或 NO)</td>
</tr>
<tr>
<td> - (void)
FB_getUserInfoComplete:NSDictionary </td>
<td>(optional)完整取得 FB 使用者基本資訊後的處理者</td>
</tr>
<tr>
<td> - (void)
FB_getAuthFndListComplete:
NSDictionary </td>
<td>(optional)完整取得 FB 使用者名單後的處理者</td>
</tr>
<tr>
<td> - (void)
FB_sharingComplete:
NSDictionary </td>
<td>(optional)FB 分享完成後的處理者</td>
</tr>
</table>
