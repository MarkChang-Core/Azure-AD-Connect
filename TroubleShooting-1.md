# Azure AD Connect 重啟後，收到告警顯示「Sync Service not running」

定期重啟Server是多數企業經常維運服務的方式之一，而臨時性的障礙也可能導致Server重啟，<br>

重啟之後有時會遭遇到 Azure AD Connect出現錯誤，你可能會透過Azure AD Connect Health收到警示，<br>

也可能通過Azure AD Connect發現到錯誤訊息，這個錯誤的畫面通常會是 - <br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image5.jpg)<br>

這個障礙的原因可能有幾種 - <br>

  1. 全域管理員於定期更改密碼後，未同步更新於Azure AD Connect。<br>
     
     在這個狀況下，請直接啟動Azure AD Connect後，更新密碼即可解決此一問題，如果忘記設定的全域管理員帳號，<br>
     
     則可透過cmd，移至 **%ProgramFiles%\Microsoft Azure AD Sync\UIShell\** 中，執行 **Miisclient.exe**<br>
     
  2. Windows Server的Services中的Azure ADSync可能停止服務。<br>
  
  3. 
