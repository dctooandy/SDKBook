#3.登入介接
###3.1 流程說明
![](../assets/isgameOAuth.png)
####3.1.1 
(1)玩家從 SDK 登入，SDK 向 iSGame OAuth 伺服器請求授權。<br>
(2)iSGame OAuth 伺服器回傳授權碼(code)給 SDK。<br>
(3)SDK 將 code 傳給用戶端(Client)。<br>
請按照 3.2 與 SDK 介接方法進行實作。

####3.1.2 
(4)用戶端將 code 傳回遊戲伺服器(Game Server)。 <br>(*傳遞方法由貴方自行完成)

####3.1.3 
(5)遊戲伺服器向 iSGame OAuth 伺服器驗證 code。 <br>
(6)驗證成功後，iSGame OAuth 伺服器回傳登入金鑰(relogin key)、 平台 uid 等參數給遊戲伺服器。<br>
請按照 3.3 與 iSGame OAuth 伺服器介接方法進行實作。

####3.1.4 
(7)遊戲伺服器將 relogin key 存至遊戲用戶端。<br> 
(*儲存方法由貴方自行完成，relogin key 應在下次登入時帶入 SDK)

***


###3.2 與 SDK 介接方法
####3.2.1 在需要 SDK 功能的檔案添加 iSGameSDK。
`#import <iSGameSDK/iSGameSDK.h>`

####3.2.2 編輯 AppDelegate.m 檔，實作`<UIApplicationDelegate>`協定。

#####(*有關`<UIApplicationDelegate>`協定功能的說明，請參考 [iOS 開發者文庫](https://developer.apple.com/reference/uikit/uiapplicationdelegate)。)



```objecttivec
-(BOOL) application:(UIApplication *) application 
        didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
    // 設定使用 IsvDelegete 的目標
    <span id = "setDelegate">[[LoginView sharedApplication] setDelegate:self];</span>
    // 設定 SDK 畫面以橫向(YES)或直向(NO)顯示;預設為 YES
    <span id = "setIsLandscape">[[LoginView sharedApplication] setIsLandscape:YES];</span>
    // 設定 SDK 介面以繁體中文(zh_TW)或英文(en)顯示;預設為系統語系(非中則英)
    [[LoginView sharedApplication] setLocalize:@"zh_TW"];
    //設定iSGameclient_id和redirect_uri
    [[LoginView sharedApplication] init:@"xxx" redirectUri:@"xxx"];
    // 提供給FB與AF SDK使用
    return [[LoginView sharedApplication] application:application
                    didFinishLaunchingWithOptions:launchOptions];
}
```

>接收來自 Google 或 Facebook 回傳的登入資訊，並返回給 iSGameSDk 處理
 
<pre>
- (BOOL) application:(UIApplication *) application
             openURL:(NSURL *) url
   sourceApplication:(NSString *) sourceApplication
          annotation:(id) annotation
{
  return [[LoginView sharedApplication] application:application
                                            openURL:url
                                  sourceApplication:sourceApplication
                                         annotation:annotation];
}
</pre>

>當選擇 Facebook 登入並從 Facebook App 返回應用裝置時，須告知 iSGameSDK

<pre>
- (void) applicationDidBecomeActive:(UIApplication *) application 
{
    [[LoginView sharedApplication] handleActiveSession];
    [[LoginView sharedApplication]
                          applicationDidBecomeActive:application];
    [super applicationDidBecomeActive:application];
}
</pre>

>提供給 AF SDK 使用

<pre>
- (BOOL) application:(UIApplication *) application
continueUserActivity:(NSUserActivity *) userActivity
  restorationHandler:(void(^)(NSArray * __nullable restorableObjects))restorationHandler
{
  return [[LoginView sharedApplication] application:application
                               continueUserActivity:userActivity
                                 restorationHandler:restorationHandler];
}
</pre>

>向 iSGameSDK 註冊推播用裝置代碼

<pre>
-(void) application:(UIApplication *) application
didRegisterForRemoteNotificationsWithDeviceToken:(NSData *) deviceToken
{
    [[LoginView sharedApplication] registDevice:deviceToken];
    [super application:application
    didRegisterForRemoteNotificationsWithDeviceToken:deviceToken];
}
</pre>

>(option)推播裝置代碼取得失敗錯誤處理

<pre>
- (void) application:(UIApplication *) application
didFailToRegisterForRemoteNotificationsWithError:(NSError *) error 
{
    [super application:application didFailToRegisterForRemoteNotificationsWithError:error];
}
</pre>


####3.2.3 實作`<IsvDelegate>`協定並產生登入頁。<br>
>iSGameSDK 初始後

<pre>
@required
- (void) initialCallback
{
    // 請依需求登出，尤其要提醒未綁定玩家，登出會造成資料遺失
    [[LoginView sharedApplication] startLogout];
    // 設定登入後取得的 relogin key，第一次登入請傳空值
    [[LoginView sharedApplication] setLoginKey:@"xxx"];
    // 產生登入頁面方法
    [[LoginView sharedApplication] startLogin];
}
</pre>

>接收 iSGameSDK 登入成功後回傳的授權碼(code)

<pre>
@required
- (void) loginComplete:(NSString *) code
- {
    // 將 code 傳送到遊戲伺服器，並由遊戲伺服器去拿回 uid、relogin key 等
    // 請參考 3.4 iSGame OAuth 伺服器返回 Game Server 資料
    // 儲 介接方使用者資訊
    //{
    // iSGameID:玩家平台 UID，若無或空值則預設為空值並 Console 提醒,
    // accountID:玩家遊戲帳號，若無或空值則預設為空值,
    // serverID:玩家遊戲伺服器 ID，若無或空值則預設為 0,
    // nickname:玩家暱稱，若無或空值則預設為空值
    //}
    [[LoginView sharedApplication] SaveGameInfo:NSDictionary];
    // 請於第一次登入(非 relogin)時，並確定已執行 SaveGameInfo 後執行下列
    [[LoginView sharedApplication] SendAFTrackEvent:@"af_login" 
                                             values:空 NSDictionary];
}
</pre>

>接收帳號綁定結果(YES 或 NO)

<pre>
@optional
-(void) bindComplete:(BOOL) isSuccess {}
</pre>

>完整取得 FB 使用者基本資訊後的處理者

<pre>
@optional
- (void) FB_getUserInfoComplete:(NSDictionary*) FBUserInfoList
{
    // valid:成功與否
    // msgid:回傳之訊息編號
    // msg:回傳之訊息內容
    // info:回傳之基本資訊，為 Facebook 回傳的 JSON 資訊，包含 id,
    // name, picture, first_name, last_name, gender, locale, link,
    // updated_time等等.
    // 若某筆資訊取得失敗，其對應的 info 為空值
}
</pre>

>完整取得 FB 使用者名單後的處理者

<pre>
@optional
- (void) FB_getAuthFndListComplete:(NSDictionary *) FBAuthFndList
{
    // isguid:使用者的 iSGame uid
    // fb_id:使用者的 FB id。若使用者使用快登或 G+登入則回傳 not authorize
    // data:已授權的好友 id, name, pictureUrl 
    //      或未授權的好友 inviteToken, name, pictureUrl。
    //      若無好友則回傳空 NSDictionary
    // event:執行取得 FB 使用者名單的函式名
}
</pre>

>FB 分享完成後的處理者

<pre>
@optional
- (void) FB_sharingComplete:(NSDictionary *) FBRequestList
{
    // valid:成功與否
    // msg:失敗或取消的訊息。若成功則回傳空值
    // data:被邀請者的 FB id。若無則回傳空陣列
    // event:執行分享的函式名
}
</pre>
***
###3.3 與 iSGame OAuth 伺服器介接方法

####3.3.1 接口位址
>https://oauth.is520.com/token.html

####3.3.2 接口說明
|接口|說明|
|--|--|
|接口協議|HTTP POST|
|返回格式|JSON|

####3.3.3 入口參數
|參數|類型|最大位數|說明|
|--|--|--|--|
|client_id|bigint|20|傳入於 [2.開發環境準備](../chap1/projectenvironment.md)取得的 client_id|
|client_secret|char|20|傳入於 [2.開發環境準備](../chap1/projectenvironment.md)取得的client_secret|
|redirect_uri|varhcar|255|傳入於 [2.開發環境準備](../chap1/projectenvironment.md)取得的redirect_uri|
|code|char|40|傳入授權碼|
|grant_type|char||請傳入"authorization_code"|

***
###3.4 iSGame OAuth 伺服器返回 Game Server 資料

####3.4.1登入成功:

|參數|說明|
|--|--|
|valid|驗證結果"true"|
|access_token|玩家存取認證代碼，切勿存至用戶端|
|refresh_token|更新 access_token 時使用|
|uid|iSGame 平台 uid|
|key|登入金鑰(relogin key)，第二次登入驗證使用。請儲存至用戶端|
|user_type|使用者登入類型(1 : 帳號登入、2 : 快速登入)|


返回資料範例:<br>
{<br>
"valid":"true",<br> "access_token":"00UtWcWm00UtWcWm00UtWcWm00UtWcWm00UtWcWm",<br> "refresh_token":"3eRqr******************************nx8JY",<br> "uid":"290******137",<br>
"key":"oooooooooooooooo", <br>
"user_type":"1"<br>
}

####3.4.2 登入失敗:

|參數|說明|
|--|--|
|valid|驗證結果"false"|
|msgId|錯誤訊息 id，請參考附錄 A. Message|
|msg|錯誤訊息，請參考附錄 A. Message|

返回資料範例:<br>
{"vaild":"false","msgId":"8","msg":"Client authentication failed"}

####3.4.3 登入完成後，貴方應於

1 遊戲伺服器儲存 uid, access_token, key, user_type。 <br>
2 用戶端儲存 uid, key, user_type。