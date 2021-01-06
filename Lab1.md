# Lab 1. 設定 Azure AD Connect

### 安裝 Azure AD Connect

- 建置完成 Server Manager 視窗中，選擇Local Server<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image1.jpg)<br>

- 將 IE Enhanced Security Configuration 設定調整為 Off。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image2.jpg)<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image3.jpg)<br>

- 開啟 IE 瀏覽器，輸入網址 https://go.microsoft.com/fwlink/?LinkId=615771 進行Azure AD Connect的下載。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image4.jpg)<br>

- 下載完成後，開啟AzureADConnect.exe，進行安裝。<br>

- 勾選「I agree to the License terms and privacy notes.」，點選「Continue」。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image5.jpg)<br>

- 選擇「Customize」以繼續安裝。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image6.jpg)<br>

- 選擇「Install」以繼續安裝流程。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image7.jpg)<br>

- 勾選 **雜湊密碼同步** - 「Password Hash Synchronization」後，按下「Next」。

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image8.jpg)<br>

- 輸入欲同步之 Azure AD 全域管理員帳號、密碼後，按下「Next」<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image9.jpg)<br>

- 點選「Add Directory」 > 選擇「Create new AD account」 > 輸入您具有 ENTERPRISE ADMIN 權限的帳號 > 按下「OK」。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image10.jpg)<br>

- 確認AD樹系已通過驗證。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image11.jpg)<br>




