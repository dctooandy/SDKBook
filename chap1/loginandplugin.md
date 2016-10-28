#3.登入介接
####3.1 流程說明
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