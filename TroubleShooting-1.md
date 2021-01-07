# Azure AD Connect 重啟後，收到告警顯示「Sync Service not running」

這個障礙的原因可能有幾種 - <br>

  1. 同步使用之帳號遭到移除 或 同步使用之系統管理員密碼遭到修改，或是帳號遺失。<br>
     
     但如果忘記同步使用的系統管理員帳號，則可依據以下步驟操作 - <br>
  
     - 透過cmd，移至 **%ProgramFiles%\Microsoft Azure AD Sync\UIShell\** 中，執行 **Miisclient.exe**<br>
     
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image5.jpg)<br>
     
     - 接著選取「連接器」，然後按兩下 Azure Active Directory 連接器後選取「連接」。
  
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image6.jpg)<br>
  
     - 此處的「UserName」值，即是用來設定目錄同步處理的全域系統管理員帳戶。
       
       ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image7.jpg)<br>
       
  2. Windows Server的Services中的Azure ADSync可能停止服務。<br>
     
     定期重啟Server是多數企業經常維運服務的方式之一，而臨時性的障礙也可能導致Server重啟，<br>

重啟之後有時會遭遇到 Azure AD Connect出現錯誤，
      
      
     ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image8.jpg)<br>
      
  3. 
