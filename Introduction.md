# 甚麼是Azure AD Connect?

Azure AD Connect 是一種 Microsoft 工具，其設計目的是要符合並完成混合式身分識別的目標。 它可提供下列功能：
 - [密碼雜湊同步處理](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-phs) - 一種將使用者內部部署 AD 密碼的雜湊與 Azure AD 同步的登入方法。<br>
 - [傳遞驗證](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-pta) - 一種登入方法，可讓使用者在內部部署環境與雲端中使用相同的密碼，但不需要額外的同盟環境基礎結構。<br>
 - [同盟整合](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-fed-whatis) - 同盟是 Azure AD Connect 的選用組件，可用來以內部部署 AD FS 基礎結構設定混合式環境。<br>
   它也提供 AD FS 管理功能，例如憑證更新及額外的 AD FS 伺服器部署。<br>
 - [同步處理](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-sync-whatis) - 負責建立使用者、群組及其他物件。 此外，也確保您內部部署使用者和群組的身分識別資訊與雲端相符。<br>
   此同步處理也包括密碼雜湊。<br>
 - [狀況監控](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-azure-ad-connect#what-is-azure-ad-connect-health) - Azure AD Connect Health 可以提供健全監控，<br>
   並在 Azure 入口網站中提供檢視此活動的中央位置。

# 為何要使用 Azure AD Connect？

將內部部署目錄與 Azure AD 整合可提供一個通用身分識別來存取雲端和內部部署資源，讓使用者變得更有生產力。使用者和組織可以利用：<br>
- 使用者可以使用單一身分識別來存取內部部署應用程式和雲端服務，例如 Microsoft 365。<br>
- 單一工具即可提供輕鬆進行同步處理和登入的部署經驗。<br>
- 提供您案例的最新功能。 Azure AD Connect 會取代舊版的身分識別整合工具，如 DirSync 和 Azure AD Sync。如需詳細資訊，請參閱 混合式身分識別目錄整合工具比較。<br>

