# Azure AD 自訂網域設定

若正在採用Microsoft 365相關服務，多數會將自有網域加入到Azure AD的自訂網域之中，本文章主要說明此加入自訂網域設定的步驟，<br>

而操作這個步驟可以透過兩個位置進行，分別為Microsoft 365 Admin center 以及 Azure Portal中的 Aure AD，<br>

而本文章將以多數使用者首次接觸 Microsoft 365時最可能開始操作的介面、即Microsoft 365 Admin Center作為主要Lab情境。<br>

但事實上，透過Azure AD設定自訂網域的過程會更為簡單，因為缺少了MX、CNAME、TXT等Microsoft 365相關服務所需紀錄的設定過程。<br>

### 新增網域

- 登入Microsoft 365之後，選擇 Admin / 系統管理。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image1.jpg)<br>

- 進入Microsoft 365 admin center之後，選擇刀鋒視窗(Blade)中的「設定」>「網域」。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image2.jpg)<br>

- 進入網域設定之後，選擇「+ 新增網域」。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image3.jpg)<br>

- 輸入所需要設定的網域名稱，並點選下方的「使用此網域」。<br>

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image4.jpg)<br>

- 接下來進入到網域驗證的環節，此處Microsoft必須驗證網域所有權，而要驗證操作的人是否為管理員，<br>

最好的方法就是確認你對於這個網域的管理全縣到哪裡，因此這邊有兩種方法可以使用 - <br>

  - **透過 TXT 或 MX Record 進行驗證 - **<br>
    
    如果你是DNS的管理員，勢必你對於這個網域有合法的管理權限，因此Microsoft會提供給您一組紀錄值，<br>
    
    並且要求你新增到DNS之中，當Microsoft的DNS能夠成功解析到你的DNS紀錄，就會回傳驗證成功。
    
    這個驗證方法非常單純，但是若你的DNS並非Microsoft所配合的域名註冊商(大多是一些國際知名的DNS註冊商，例如Godaddy、Gandi...等)<br>
    
    那麼等待DNS的紀錄值生效會需要4 - 24小時，甚至更久。<br>
    
    ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image5.jpg)<br>
    
  - **將指定文字新增到對應Domain的網址的指定路徑之中 - **<br>

    如果你是網頁伺服器的管理員，當然也代表你正合法的代表這個網域進行這項操作，因此如果你選擇這項驗證方式，<br>
    
    Microsoft將會提供給你一組亂數的TXT文本資訊，要求你新增到網站的根目錄之中，例如本Lab中選擇此方式則路徑將為 - 

    ** www.zerone-lab.com/ms50589532.txt 或 zerone-lab.com/ms50589532.txt **
    
    因此當然這個方式會比起DNS更快速，但前提是必須要取得網頁伺服器的管理權限才可以進行。
    
    ![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image6.jpg)<br>
    
- 完成驗證設定後，若有使用Microsoft 365的相關其他服務(如Exchange Online / Teams...)，即可點擊「繼續」，若無則可點擊關閉。

![GITHUB](https://github.com/MarkChang-Core/AADC/blob/main/image2/image7.jpg)<br>
    

    
