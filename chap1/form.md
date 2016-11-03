#13.申請表單
###13.1 <a name="dele">貴方應提供資料項目</a>


| 序 | 名稱 | 說明 | 填入資料 |
| :--: | -- | -- | -- |
| 1 | <font color="orange">Bundle Identifier <br>(Bundle ID)</font> <br><font color="darkpink">required</font> | 請提供貴方上架的<br>Bundle Identifier (App ID Suffix)<br>ex:com.domainname.appname |  |
| 2 | <font color="orange">推播用憑證<br>(APNs Certificates)</font> <br><font color="darkpink">required</font> | 若需使用推播功能，<br>請提供貴方的推播用憑證<br>ex:appname.pem | 提供方式請聯繫<br>iSGame 平台窗口 |
| 3 | <font color="orange">FB 客製邀請動作<br>(send / askfor)</font> <br><font color="darkpink">optional</font> | 若需使用 FB 客製邀請功能，<br>請填寫使用「send」或「askfor」，<br>可提供客製化翻譯(中文或其他語言)| 其他行為請聯繫<br>iSGame 平台窗口 |
| 4 | <font color="orange">FB 客製邀請物品<br>(item)</font> <br><font color="darkpink">optional</font> | 承 3，請填寫客製邀請使用的物品名<br>稱，與 3 可多組搭配，預設是英文，<br>可提供客製化翻譯(中文或其他語言) |  |
| 5 | <font color="orange">FB 自動分享審核資料<br>(publish_actions)</font> <br><font color="darkpink">optional</font> | 若需使用 FB 自動分享功能，<br>需申請 FB publish_actions 權限，<br>請提供對應審核資料 |  |
| 6 | <font color="orange">Apple App ID<br>(應為一串數字)</font> <br><font color="darkpink">optional</font> | 若需使用 AppsFlyer 分析功能，<br>請提供貴方上架的<br>Apple App ID |  ||


###13.2 貴方應獲得資料項目
| 序 | 名稱 | 說明 |
| :--: | -- | -- |
| 1 | <font color="blue">iSGame-iOS-SDK.zip</font><br><font color="dark">required</font> | iSGame SDK，為壓縮檔 |
| 2 |  Facebook <font color="blue">app_id</font><br><font color="dark">required</font> | 呼叫 Facebook 登入時的身分標誌，請妥善保管 |
| 3 | Facebook <font color="blue">scheme</font><br><font color="dark">required</font> | 呼叫 Facebook Deep linking 的 scheme 名稱 |
| 4 | Facebook <font color="blue">object ID</font><br><font color="dark">required</font> | 對應 FB 客製邀請物品的 id 編號 |
| 5 | Facebook <font color="blue">Applink</font><br><font color="dark">required</font> | 申請 FB 自動分享審核資料通過後的 openurl 網址 |
| 6 | Google <font color="blue">Client ID</font><br><font color="dark">required</font> | 呼叫 Google+登入時的身分標誌，請妥善保管 |
| 7 | iSGame <font color="blue">client_id</font><br><font color="dark">required</font> | 呼叫 iSGame SDK 功能時的身分標誌，請妥善保管 |
| 8 | iSGame <font color="blue">client_secret</font><br><font color="dark">required</font> | 呼叫 iSGame SDK 功能時的密鑰，請妥善保管 |
| 9 | iSGame <font color="blue">redirect_uri</font><br><font color="dark">required</font> | iSGame 平台驗證用，請妥善保管 |
| 10 | AppsFlyer <font color="blue">Dev Key</font><br><font color="dark">required</font> | 呼叫 AppsFlyer 功能時的身分標誌，請妥善保管 |
