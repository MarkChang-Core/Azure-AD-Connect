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

- 
