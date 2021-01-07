# Synchronization Rule Editor

Azure AD Connect主要是針對OU或篩選過後的使用者進行同步，但若要屏除掉一些使用者夾帶的屬性，則可使用Synchronization Rule Editor，<br>

這項工具是夾帶於Azure AD Connect中一併安裝的，因此您可以在Azure AD Connect的路徑中找到他。<br>

### 本Lab將透過以下情境進行操作的分享 - 

當企業評估Exchange Online的導入時，相當程度可能是因為既有的Exchange Server版本過舊且升級成本太高的關係，<br>

因此選擇分批將使用者遷移到Microsoft 365 Exchange Online之中，混合雲佈署方式的確是在企業從On-pre進入Pure Cloud過渡期解決方案，<br>

這個狀況下多數MIS會觀望[Exchange Server混合式部署](https://docs.microsoft.com/zh-tw/exchange/exchange-hybrid)的情境，但Exchange Server的Hybrid mode又會存在Exchange Server的[版本要求](https://docs.microsoft.com/zh-tw/exchange/hybrid-deployment-prerequisites)的問題，<br>

若要滿足版本要求，則又回到Exchange Server版本升級成本太高的癥結點，因此這時則會有企業決定捨棄Exchange Server，<br>

全面採用Exchange Online。<br>


但企業並不會因為全面採用Exchange Online而同時一併捨棄On-pre的Windows AD，畢竟其中多數會擁有Device Joining Domain的可能，<br>

因此這時便會期望通過Azure AD Connect將名單目錄抄寫至Azure AD之上，而持續保留On-pre的Windows AD，<br>

但由於使用者屬性中多數已夾帶了Exchange Server的屬性，這時若直接執行Azure AD Connect，可能會發生不可預期的錯誤，<br>

例如msExchMailboxGuid中，若存在Exchange Server mailbox的屬性時，這些被抄寫的使用者將可能無法配置Exchange Online mailbox，<br>

甚至被抄寫後，成為Exchange Online中的全域連絡人，這時便可通過Synchronization Rule Editor來排除掉Source的屬性抄寫。<br>

以下將針對上述情境進行 Synchronization Rule Editor 的操作。<br>


### 設定 Synchronization Rule Editor

- 當您安裝完成Azure AD Connect之後，在Azure AD Connect路徑之下可以找到Synchronization Rule Editor<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image3/image1.jpg)<br>

- 開啟 Synchronization Rule Editor 後，找到 **Infrom AD - User Exchange**，接著點選下方的Edit。<br>

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image3/image2.jpg)<br>

- 開啟編輯模式後，選擇左側的Transformations，並找尋「msExchMailboxGuid」，接著將前方的FlowType更改為Expression，<br>

  並勾選後方的Apply Once，並將Source欄位中的值修改為**AuthoritativeNull**，修改完成後點選下方的「Save」<br>
  
  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image3/image3.jpg)<br>
  
- 儲存完成後，會出現Warning，內容主要描述為這項修改會在下次同步時被執行，如此便完成。

  ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/Image3/image4.jpg)<br>

### 驗證屬性同步狀況

  修改完成後，可以在下次同步後觀察Azure AD中的同步狀況，若成功的話，可以發現同步上來的User已經可以順利指派Exchange Online mailbox。
