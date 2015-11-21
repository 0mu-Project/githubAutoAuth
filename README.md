# githubAutoAuth
自動登入github並把commit Push到gitHub的工具。

## 緣起
想用CGI接GitHub認證，讓CGI可以上傳檔案後自動認證並Commit。但卻找不到方法可以「跳過問答模式」登入，我們又不想管理私鑰，就在尋找各種解決方案。最後發現gitHub的https可以直接透過修改`remote.origin.url`做到，假如原本是`https://github.com/0mu-Project/Example`，只要改成`https://username:password@github.com/0mu-Project/Example`就可以自動使用帳號密碼驗證。

## 用途
CGI間接，或是其他沒有console但是想透過帳號密碼認證GitHub並Push Commit的場合。

## 流程

1. 先檢查原本的網址中有沒有認證資訊（`username:password@`），如果有先刪掉
2. 將`remote.origin.url`加入認證資訊
3. 執行git push
4. 把`remote.origin.url`當中的認證資訊刪掉


