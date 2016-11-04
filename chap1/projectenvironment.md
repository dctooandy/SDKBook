#2.開發環境準備
####2.1 韌體最低版本
iSGame SDK 僅支援 iOS 7.0 以上韌體，貴方請確保測試環境不低於此版本

####2.2 您需要給 iSGame 平台的遊戲相關資料
>貴方應把以下資料交給您聯繫的 iSGame 平台窗口。 <br>
>>1. Bundle Identifier (Bundle ID)<br>
>>2. 推播用憑證 (APNs Certificates)<br>
>>3. FB 客製邀請動作 (send / askfor)<br>
>>4. FB 客製邀請物品 (item)<br>
>>5. FB 自動分享審核資料 (publish_actions) ○6 Apple App ID (應為一串數字)<br>
>>請參考 13.申請表單。

####2.3 iSGame 平台必須給您的遊戲介接資料
>iSGame 平台窗口確認收到 2.2 的資料後，將回覆貴方以下資料。<br>
>>1. iSGame-iOS-SDK.zip<br>
>>2. Facebook app_id<br>
>>3. Facebook scheme<br>
>>4. Facebook object ID<br>
>>5. Facebook Applink<br>
>>6. Google Client ID<br>
>>7. iSGame client_id<br>
>>8. iSGame client_secret <br>
>>9. iSGame redirect_uri <br>
>>10. AppsFlyer Dev Key <br>
>>請參考 [13.申請表單]()。

####2.4 在 Xcode 設定遊戲專案環境
依照以下方法編輯專案的.plist 檔，加入 2.3 取得的 Facebook scheme、app_id 與 Google Client ID 與 iSGame client_id、redirect_uri 與 AppsFlyer Dev Key。

```objectiveC
URL types
    Item 0
        URL Schemes
              Item 0 => xxx(填入取得的 Facebook scheme) 
    Item 1(Editor)
        Document Role => Editor
        Identifier => xxx(填入專案的 Bundle ID) URL Schemes
        URL Schemes
              Item 0 => xxx(填入專案的 Bundle ID)        
FacebookAppID => xxx(填入取得的 Facebook app_id) FacebookDisplayName => xxx(填入專案名稱) 
NSAppTransportSecurity (選 Dictionary)
    NSExceptionDomains (選 Dictionary) 
        facebook.com (選 Dictionary)
              NSIncludesSubdomains => YES
              NSExceptionRequiresForwardSecrecy => No
        fbcdn.net (選 Dictionary)
              NSIncludesSubdomains => YES
              NSExceptionRequiresForwardSecrecy => No
        akamaihd.net (選 Dictionary)
              NSIncludesSubdomains => YES
              NSExceptionRequiresForwardSecrecy => No
LSApplicationQueriesSchemes
    Item 0 => fbapi
    Item 1 => fb-messenger-api 
    Item 2 => fbauth2
    Item 3 => fbshareextension     
GoogleClientId => xxx(填入取得的 Google Client ID)
ISGameClientId => xxx(填入取得的 iSGame client_id)
ISGameRedirectURI => xxx(填入取得的 iSGame redirect_uri)
AppsFlyerDevKey => xxx(填入取得的 AppsFlyer Dev Key)
AppleAppID => xxx(填入貴方的 Apple App ID，應為一串數 )          
AFDeviceTrackingDisabled => No(是否取消追蹤功能，若介接方不想使用
AppsFlyer 請設為 Yes，建議且預設為 No 意即開啟追蹤)
AFCurrencyCode => TWD(貨幣代碼，預設為 TWD，代碼請參考這裡。這邊要特別注意 若之後的 trackEvent 有帶 af_currency(AFEventParamCurrency)此參數，則此事件會以 af_currency 為主)
View controller-based status bar appearance => No 
Status bar is initially hidden => Yes 
UIRequiresFullScreen => Yes
```



####2.5 將 SDK 匯入專案

將 iSGame-iOS-SDK.zip 裡的 6 個資料夾加進專案《frameworks》目錄裡或任 意位置再新增專案裡 Targets→Build Settings 中的 Search Paths 之「Framework Search Paths」。<br>

1. `《ISGameSDK.bundle》`
2. `《ISGameSDK.framework》`
3. `《FBSDKCoreKit.framework》` 
4. `《FBSDKLoginKit.framework》` 
5. `《FBSDKShareKit.framework》` 
6. `《AppsFlyerLib.framework》`



####2.6 添加所需 bundle 與 frameworks
專案裡選擇 Targets→Build Phases，在 Copy Bundle Resources 引入 《ISGameSDK.bundle》，在 Link Binary With Libraries 引入以下 19 個 frameworks，除 Adsupport.framework 為 Optional 其餘皆為 Required。

01. `《ISGameSDK.framework》`
02. `《FBSDKCoreKit.framework》` 
03. `《FBSDKLoginKit.framework》` 
04. `《FBSDKShareKit.framework》` 
05. `《AppsFlyerLib.framework》` 
06. Adsupport.framework
07. iAd.framework
08. Accounts.framework
09. AddressBook.framework
10. AssetsLibrary.framework
11. CoreGraphics.framework
12. CoreLocation.framework
13. CoreMotion.framework
14. CoreText.framework
15. Foundation.framework
16. MediaPlayer.framework
17. Security.framework
18. SystemConfiguration.framework 
19. UIKit.framework



 