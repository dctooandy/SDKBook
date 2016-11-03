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
