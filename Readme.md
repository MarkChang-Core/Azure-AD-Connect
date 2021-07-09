# 甚麼是Azure AD Connect?

Azure AD Connect 是一種 Microsoft 工具，其設計目的是要符合並完成混合式身分識別的目標。 它可提供下列功能：
 - [密碼雜湊同步處理](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-phs) - 一種將使用者內部部署 AD 密碼的雜湊與 Azure AD 同步的登入方法。<br>
 - [傳遞驗證](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-pta) - 一種登入方法，可讓使用者在內部部署環境與雲端中使用相同的密碼，但不需要額外的同盟環境基礎結構。<br>
 - [同盟整合](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-fed-whatis) - 同盟是Azure AD Connect的選用組件，可用來以內部部署AD FS基礎結構設定混合式環境。<br>
   它也提供 AD FS 管理功能，例如憑證更新及額外的 AD FS 伺服器部署。<br>
 - [同步處理](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/how-to-connect-sync-whatis) - 負責建立使用者、群組及其他物件。此外，也確保您內部部署使用者和群組的身分識別資訊與雲端相符。<br>
   此同步處理也包括密碼雜湊。<br>
 - [狀況監控](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-azure-ad-connect#what-is-azure-ad-connect-health) - Azure AD Connect Health 可以提供健全監控，<br>
   並在 Azure 入口網站中提供檢視此活動的中央位置。

# 為何要使用 Azure AD Connect？

將內部部署目錄與 Azure AD 整合可提供一個通用身分識別來存取雲端和內部部署資源，讓使用者變得更有生產力。使用者和組織可以利用：<br>
- 使用者可以使用單一身分識別來存取內部部署應用程式和雲端服務，例如 Microsoft 365。<br>
- 單一工具即可提供輕鬆進行同步處理和登入的部署經驗。<br>
- 提供您案例的最新功能。 Azure AD Connect 會取代舊版的身分識別整合工具，如 DirSync 和 Azure AD Sync。如需詳細資訊，請參閱 混合式身分識別目錄整合工具比較。<br>

# 內部部署 Active Directory 必要版本

- Active Directory 架構版本和樹系功能等級必須是 Windows Server 2003 或更新版本。 只要符合架構版本和樹系層級的需求，網域控制站就可以執行任何版本。<br>
- 如果您打算使用功能 密碼回寫，則網域控制站必須在 Windows Server 2012 或更新版本上。<br>
- Azure AD 使用的網域控制站必須為可寫入。 不支援 使用唯讀網域控制站 (RODC) ，而且 Azure AD Connect 不會遵循任何寫入重新導向。<br>
- 使用內部部署樹系或網域（使用「點點」 (名稱包含句點 "."）。 不支援) NetBIOS 名稱。<br>
建議您 啟用 Active Directory 回收站。<br>

# Azure AD Connect 安裝必要條件

### 環境要求

- Azure AD Connect 必須安裝在已加入網域的 Windows Server 2012 或更新版本上。<br>
- Azure AD Connect 無法安裝在2019之前的 Small Business Server 或 Windows Server Essentials () 支援 Windows Server Essentials 2019。 伺服器必須使用 Windows Server Standard 或以上版本。
- Azure AD Connect 伺服器必須已安裝完整的 GUI。 不支援在 Windows Server Core 上安裝 Azure AD Connect。<br>
- 如果您使用 Azure AD Connect wizard 來管理 Active Directory 同盟服務 (AD FS 設定，Azure AD Connect 伺服器就不能群組原則啟用 PowerShell 轉譯。 如果您使用 Azure AD Connect wizard 來管理同步處理設定，則可以啟用 PowerShell 轉譯。<br>
- 如果正在部署 AD FS：<br>
  - 安裝 AD FS 或 Web 應用程式 Proxy 的伺服器必須是 Windows Server 2012 R2 或更新版本。 Windows 遠端管理 ，才能執行遠端安裝。<br>
  - 您必須設定 TLS/SSL 憑證。 如需詳細資訊，請參閱在 AD FS 中管理 AD FS 和管理 ssl 憑證的 ssl/TLS 通訊協定和加密套件。<br>
  - 您必須設定名稱解析。<br>
- 如果您的全域管理員已啟用 MFA，則 URL https://secure.aadcdn.microsoftonline-p.com 必須 在 [信任的網站] 清單中。 當系統提示您提供 MFA 挑戰，但尚未新增之前，系統會提示您將此網站新增至 [信任的網站] 清單。 您可以使用 Internet Explorer 將它新增到信任的網站。

### 元件要求

Azure AD Connect 需要 Microsoft PowerShell 和 .NET Framework 4.5.1。 您需要在伺服器上安裝此版本或更新版本。 視您的 Windows Server 版本而定，採取下列動作：<br>
- Windows Server 2012 R2<br>
  - 預設會安裝 Microsoft PowerShell。 您不需要執行任何動作。<br>
  - .NET Framework 4.5.1 和更新版本會透過 Windows Update 提供。 請確定您已在主控台中安裝最新的 Windows Server 更新。<br>
- Windows Server 2012<br>
  - 您可以從 Microsoft 下載中心取得的 Windows Management Framework 4.0 提供最新版本的 microsoft PowerShell。<br>
  - 您可以從 Microsoft 下載中心取得 .NET Framework 4.5.1 和更新版本。<br>

### Azure AD Connect 的硬體需求

下表顯示 Azure AD Connect 同步電腦的最低需求。<br>

|    **Active Directory 中的物件數目**   | **CPU** | **Memory** | **Disk** |
| ----------------- | :----: | :----: | :----: |
| 少於 10,000 個 | 1.6 GHz | 4 GB | 70 GB |
| 10,000–50,000 個 | 1.6 GHz | 4 GB | 70 GB |
| 50,000–100,000 個 | 1.6 GHz | 16 GB | 100 GB |

若為100000或更多物件，則需要 SQL Server 的完整版本。<br>

|    **Active Directory 中的物件數目**   | **CPU** | **Memory** | **Disk** |
| ----------------- | :----: | :----: | :----: |
| 100,000–300,000 個 | 1.6 GHz | 32 GB | 300 GB |
| 300,000–600,000 個 | 1.6 GHz | 32 GB | 450 GB |
| 超過 600,000 個 | 1.6 GHz | 32 GB | 500 GB |

更多詳細資料請參考：[Microsoft Azure AD Connect](https://docs.microsoft.com/zh-tw/azure/active-directory/hybrid/whatis-azure-ad-connect#what-is-azure-ad-connect-health)<br>

### 其他你可以參考的事情 (2020.12.11)

- Azure AD Connect並不是雙向同步的工具，而是將Windows AD中的名單目錄單向抄寫至Azure AD之中。<br>

- 如果先透過了Azure AD建立使用者、再建置Windows AD，那麼Azure AD Connect將無法將使用者同步回到Windows AD的。<br>

- 若是透過Azure AD Connect抄寫至Azure AD的使用者，其驗證將是發生在Azure AD之上。<br>

- Azure AD Connect通常建置與Windows AD同網段、不同Server(VM)中，但有些企業基於Windows AD的負載非常輕，<br>

  會考慮建置同台Server，但請務必留意，當服務有問題需要重啟時，可能會影響到Windows AD的運作，因此相對還是建議分離。<br>

- 若情境中的Windows AD是建置於Azure VM之中，仍舊需要建置Azure AD Connect方可將名單目錄抄寫至Azure AD之中。<br>

- 純雲端的AD環境，可考慮將身分建置於Azure AD中，不需要建置Azure AD Connect，但可評估建置Azure AD Domain Service。<br>

開始建立 Azure AD Connect，請前往 [Lab 1](https://github.com/MarkChang-Core/AADC/blob/main/Lab1.md)
