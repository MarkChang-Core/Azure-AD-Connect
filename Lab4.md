# 關於 Windows AD 如何新增別名

由於許多使用者於完成Azure AD Connect後，會將On-premise的AD屬性抄寫至Azure AD之中，<br>

在這之後便無法於Microsoft 365或是Azure AD之中編輯屬性、而需要回到On-premise的AD中操作，<br>

其中最多管理員的疑問皆是「那麼該如何編輯使用者別名?」<br>

註：此情境可能不適用於透過Exchange Server 擴充 AD Schema 的屬性。<br>

### 如何操作於Windows AD中寫入別名?

情境：預設該位使用者即有存在 User Account，例如是 user01@yourdomain.com，需要新增別名為 user01@youralias.com<br>

- 請開啟 Windows Server 中的 Active Directory -<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image1.jpg)<br>

- 點擊上方的 「檢視(View)」 > 「進階功能(Advance Feature)」<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image2.jpg)<br>

- 找到您需要編輯的使用者，對其點選右鍵，選擇「內容(Properties)」<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image3.jpg)<br>

- 找到頁籤中的「屬性編輯器(Attribute Editor)」，並找尋 屬性 proxyAddress 後，點選 編輯(Edit)<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image4.jpg)<br>

- 輸入別名為 smtp:user01@youralias.com 後，點選「增加(Add)」，再點選「確定(OK)」

  **請留意，此處 ```smtp:``` 代表郵件別名，而 ```SMTP:``` 則代表主要電子郵件，大、小寫請特別留意。**

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image5.jpg)<br>

接下來，等待30分鐘使其自行同步至Azure AD之中，您便會看到該位使用者已擁有別名 -

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image6/image6.jpg)<br>

此外，您也可以透過指令，於On-premise的Active Directory之中執行 - 

```Start-ADSyncSyncCycle -PolicyType Delta```

