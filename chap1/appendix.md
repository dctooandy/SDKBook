# 附錄

###附錄 A. Message
| msgid | msg | 備註 |
| :--: | -- | -- |
| 0 | The request is missing a required parameter, includes<br> an invalid parameter value, includes a parameter more<br> than once, or is otherwise malformed. Check the "%s"<br> parameter | 傳遞參數短少 |
| 1 | The client is not authorized to request an access token<br> using this method | 此 client_id 無法使用此方式 進行驗證 |
| 2 | The resource owner or authorization server denied the<br> request | 此 user 被拒絕存取/或 server 拒絕此請求 |
| 3 | The authorization server does not support obtaining an<br>access token using this method | response_type 錯誤 |
| 4 | The requested scope is invalid, unknown, or<br> malformed. Check the "%s" scope | scope 參數驗證錯誤 |
| 5 | The authorization server encountered an unexpected<br> condition which prevented it from fulfilling the request | 2:7 |
| 6 | The authorization server is currently unable to handle<br> the request due to a temporary overloading or<br> maintenance of the server | 2:8 |
| 7 | The authorization grant type "%s" is not supported by<br> the authorization server | 2:9 |
| 8 | Client authentication failed | 2:10 |
| 9 | The provided authorization grant is invalid, expired,<br> revoked, does not match the redirection URI used in<br> the authorization request, or was issued to another<br> client. Check the "%s" parameter | 2:11 |
| 200 | Success | 2:12 |
| 998 | FB message | 2:13 |
| 999 | Else message | 2:14 |
