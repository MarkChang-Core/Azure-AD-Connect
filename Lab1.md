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

- 確認AD樹系已通過驗證後，按下「Next」前往下一步。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image11.jpg)<br>

- 此步驟請確認Windows AD Domain Service樹系名稱一致，且Azure AD Domain狀態為「Verified」，請點選「Next」進行下一步。<br>
  
  - 正常狀態於此步驟 Azure AD Domain 狀態應該是 Verified 狀態 - <br>
  
    ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image12.jpg)<br>
  
  - 若狀態顯示為 Not Add，則請參考 [此步驟](https://github.com/MarkChang-Core/AADC/blob/main/Lab2.md) 進行 Azure AD 自訂網域設置 - <br>
  
    但若不想在這個階段就進行自訂網域設定，也可以勾選 **Continue without matching all UPN suffixes to verified domains** 後繼續操作。

    ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image13.jpg)<br>

- 選擇「Sync selected domains and OUs」，並選擇預計同步的OU後，按下「Next」前往下一步設定。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image14.jpg)<br>

- 直接按下「Next」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image15.jpg)<br>

- 如需要對 name / DN 等屬性進行篩選可於此設定，若無則保持 Synchronize all users and devices，並點擊「Next」繼續。

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image16.jpg)<br>

- 直接按下「Next」。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image17.jpg)<br>

- 按下「Install」後，開始進行設置。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image18.jpg)<br>

- 完成同步。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image/image19.jpg)<br>
