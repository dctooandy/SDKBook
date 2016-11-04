#4.帳號綁定介接

###4.1 流程說明
快速登入的玩家可藉由貴方提供「帳號綁定」之按鈕，進行帳號綁定流程。<br>
已綁定帳號的玩家可查看帳號資訊。

###4.2 程式實作
<span id="startBinding"></span>

>// 快登綁定方法，參數為登入者的 uid<br>
>[[LoginView sharedApplication] startBinding:@"xxx"];

