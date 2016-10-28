#1.文件說明

>##### 本文件說明 iSGame SDK 的介接過程。<br>iSGame SDK 是 iSGame 開發的移動平台套件，提供遊戲開發商(以下稱貴方)<br>在資源整合上的優秀解決方案;貴方 可善用本 SDK 為玩家提供更全面的服務。


#1.1 iSGame SDK 功能

####iSGame SDK 具備以下功能:

####帳號登入-
>iSGame SDK 採用 Oauth2.0 授權機制，提供玩家下列三種登入方式:<br>
>>1 Facebook 帳號登入。<br>
>>2 Google+帳號登入。<br>
>>3 快速登入:玩家可直接進行遊戲，不必登入帳號。 <br>請參考 3.登入介接。

####接續遊戲-
>玩家再次啟動遊戲時可直接取回遊戲進度。 <br>
貴方需完成登入金鑰(relogin key)驗證。請參考 3.登入介接。

####帳號綁定-
>快速登入的玩家如果想避免遊戲資料遺失，可利用 Facebook 帳號或 Google+帳號綁定遊戲。請參考 4.帳號綁定介接。

####客服回報-
>玩家在遊戲中可線上回報問題。請參考 5.客服回報介接。 

####遊戲活動及遊戲公告-
>玩家可查看由 iSGame 平台發佈之遊戲活動與公告訊息。
請參考 6.遊戲活動介接與 7.遊戲公告介接。 

####中/英文顯示介面-
>以上功能皆備有繁體中文介面與英文介面，貴方可視需求設
定 iSGame SDK 顯示的介面語系。請參考 3.2 與 SDK 介接方法。

####Facebook 社交功能-
>貴方可透過 SDK 讓 Facebook 玩家發送遊戲邀請，並取得 邀請成員名單。請參考 8.Facebook 使用者名單撈取介接與
9.Facebook 分享功能介接。

####AppsFlyer 分析功能-
>貴方可透過 SDK 寄送追蹤事件以便之後分析。請參考
10.AppsFlyer 介接。 

####通知推播-
>玩家可收到遊戲的提醒通知。請參考 11.訊息推播(APNS)。 

####登入屏蔽-
>可防止玩家登入正在停機維護的遊戲。請參考 12.登入屏蔽。

#1.2 iSGame SDK 標準版/輕量版功能摘要
|<center>主功能</center>|<center>子功能</center>|iSGame SDK<br> 標準版|iSGame SDK <br>輕量版|
|--|--|--|--|
|客服|回報問題<br>檢視個人回報記錄|<center>&#9745;</center>|<center>&#9745;</center>|
| 會員系統|資料記錄<br>平台儲值<br>領取禮包|<center> &#9745;</center>||
|登入&註冊會員|快登(試玩帳號登入)<br>FB 帳號登入<br> Google+帳號登入<br>同意服務條款 <br>快登提醒<br> 完成登入 callback|<center> &#9745;</center>||
|快登會員綁定|FB 帳號綁定<br>Google+帳號綁定<br>完成綁定 callback|<center> &#9745;</center>||
|公告|遊戲公告<br>活動公告|<center> &#9745;</center>||
|推播訊息|全體玩家推播<br>指定玩家推播|<center> &#9745;</center>||
|介面語系|中文介面<br>英文介面|<center> &#9745;</center>||
|版面方向|直版畫面<br>橫版畫面|<center> &#9745;</center>||
|Appsflyer追蹤|儲值(付費比、付費轉換率、ARPU)<br>下載來源(CPC)<br>啟動(DAU)<br>安裝(CPI)<br> 遊戲節點(玩家通過數)|<center> &#9745;</center>|<center> &#9745;</center>|
|FB 社群|取得玩家FB 資訊 <br> 分享貼文 <br> 公版邀請<br>  客製化邀請|<center> &#9745;</center>||
|維護/內測支援|阻擋任意 IP 連線|<center> &#9745;</center>||
|登出會員||<center> &#9745;</center>||

<center> &#9745;</center>
