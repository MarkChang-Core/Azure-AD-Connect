# Azure AD Connect 重啟後，收到告警顯示「Sync Service not running」

這個障礙的原因可能有幾種 - <br>

  1. Windows Server的Services中的Azure ADSync可能停止服務。<br>
     
     定期重啟Server是多數企業經常維運服務的方式之一，而臨時性的障礙也可能導致Server重啟，<br>

     而重啟之後有時會遭遇到 Azure AD Connect出現錯誤 -    
      
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image5.jpg)<br>
     
     這很有可能是Microsoft Azure ADSync這項Services停止服務，此時可以依據以下步驟操作 - 
     
     a. 在「開始」中，選取「執行」，並輸入 services.msb
     
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image6.jpg)<br>
     
     b. 
     
  3. 同步使用之帳號遭到移除 或 同步使用之系統管理員密碼遭到修改，或是帳號遺失。<br>
     
     但如果忘記同步使用的系統管理員帳號，則可依據以下步驟操作 - <br>
  
     - 透過cmd，移至 %ProgramFiles%\Microsoft Azure AD Sync\UIShell\ 中，執行 **Miisclient.exe**<br>
     
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image5.jpg)<br>
     
     - 接著選取「連接器」，然後按兩下 Azure Active Directory 連接器後選取「連接」。
  
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image6.jpg)<br>
  
     - 此處的「UserName」值，即是用來設定目錄同步處理的全域系統管理員帳戶。
       
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image5/image7.jpg)<br>
