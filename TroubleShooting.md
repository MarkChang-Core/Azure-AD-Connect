# Azure AD Connect 可能遭遇障礙 (陸續更新中...)

由於Azure AD Connect為混合身分佈署中相當重要的角色，因此Azure AD Connect將會連帶提供[Azure AD Connect Health](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-azure-ad-connect#why-use-azure-ad-connect-health)，<br>

這項工具將隨時檢查連接的健康狀況，並針對異常狀況發出警示信件給予全域管理員，而全域管理原則可針對收到的警示進行障礙排除。<br>

而Azure AD Health的介面則在Azure AD之中可以找到 - <br>

- 登入Azure AD Portal，並於刀鋒視窗(Blade)中，找到Azure AD Connect，即可於下方找到Azure AD Connect Health。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image1.jpg)<br>

- 於Azure AD Connect Health之中，即可檢視同步服務、同步錯誤等監控訊息，進而檢視到同步的Error Log。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image2.jpg)<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image3.jpg)<br>

- 當抄寫狀態出現異常時，也會收到由 azure-noreply@microsoft.com 寄出的Alert，其中也包含建議的動作等資訊。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image4/image4.jpg)<br>

### 常見的Azure AD Connect障礙問題與解決方式

- Azure Active Directory 目錄同步處理停止 - [請點我了解](https://github.com/MarkChang-Core/AADC/blob/main/TroubleShooting-1.md)

- 如何停止 Azure AD Connect抄寫? - [請點我了解]()
