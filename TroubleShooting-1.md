# Azure Active Directory 目錄同步處理停止

這個障礙的原因可能有幾種 - <br>

1. Windows Server的Services中的Azure ADSync可能停止服務。<br>
     
   定期重啟Server是多數企業經常維運服務的方式之一，而臨時性的障礙也可能導致Server重啟，<br>

   而重啟之後有時會遭遇到 Azure AD Connect出現錯誤 -    
      
   ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image5.jpg)<br>
     
   這很有可能是Microsoft Azure ADSync這項Services停止服務，此時可以依據以下步驟操作 - 
     
   - 在「開始」中，選取「執行」，並輸入 services.msb
     
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image6.jpg)<br>
     
   - 找到 Microsoft Azure ADSync，點擊右鍵選擇Start，等待Status顯示為Running即可再次嘗試同步。<br>
     
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image7.jpg)<br>     
     
2. 同步使用之帳號遭到移除 或 同步使用之系統管理員密碼遭到修改，或是帳號遺失。<br>
     
   如果透過上述步驟確認Microsoft Azure ADSync已經為Running狀態，但Azure AD Connect仍然無法同步，<br>
   
   則需要檢查執行Azure ADSync的帳號是否遺失或密碼遭到更新，這裡透過以下方式進行確認 - <br>
   
   - 在Microsoft Azure ADSync中，雙擊滑鼠左鍵，並選擇頁籤為「Log On」後，確認帳號仍舊存在，<br>
   
     若帳號或密碼遺失，則請重新輸入後點選「OK」
     
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image8.jpg)<br>  
   
   - 如果上述步驟中的帳號遭變更為Local System account，且下方登入帳號遺失，同時你也忘記了這裡的登入帳號，<br>
   
     則可透過下列方式找回 - <br>
    
     - 透過cmd，移至 %ProgramFiles%\Microsoft Azure AD Sync\UIShell\ 中，執行 **Miisclient.exe**<br>
     
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image9.jpg)<br>
     
     - 接著選取「Connectors」，然後左鍵雙擊「Windows Azure Active Directory (Microsoft)」後選擇Connectivity」。<br>
     
       此處的「UserName」值，即是用來設定目錄同步處理的全域系統管理員帳戶。<br>
  
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image10.jpg)<br>
 
