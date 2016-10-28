#3.登入介接
####3.1 流程說明
![](../assets/isgameOAuth.png)
####3.1.1 
(1)玩家從 SDK 登入，SDK 向 iSGame OAuth 伺服器請求授權。<br>
(2)iSGame OAuth 伺服器回傳授權碼(code)給 SDK。<br>
(3)SDK 將 code 傳給用戶端(Client)。<br>
請按照 3.2 與 SDK 介接方法進行實作。