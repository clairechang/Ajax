
#Ajax
AJAX即「Asynchronous JavaScript and XML」（非同步的JavaScript與XML技術），指的是一套綜合了多項技術的瀏覽器端網頁開發技術。
使用Ajax的最大優點，就是能在不更新整個頁面的前提下維護資料。這使得Web應用程式更為迅捷地回應用戶動作，並避免了在網路上傳送那些沒有改變的資訊。
傳統的Web應用允許用戶端填寫表單（form），當送出表單時就向網頁伺服器傳送一個請求。伺服器接收並處理傳來的表單，然後送回一個新的網頁，但這個做法
浪費了許多頻寬，因為在前後兩個頁面中的大部分HTML碼往往是相同的。由於每次應用的溝通都需要向伺服器傳送請求，應用的回應時間依賴於伺服器的回應時間
。這導致了使用者介面的回應比本機應用慢得多。
與此不同，AJAX應用可以僅向伺服器傳送並取回必須的資料，並在用戶端採用JavaScript處理來自伺服器的回應。因為在伺服器和瀏覽器之間交換的資料大量減少
（大約只有原來的5%）[來源請求],伺服器回應更快了。同時，很多的處理工作可以在發出請求的用戶端機器上完成，因此Web伺服器的負荷也減少了。

####Syntax

程式範例: 點擊一個按鈕，做一些什麼事情。
因此可以這樣寫：
```html
<script>
         var Submit=function(){
            var URLs="recive.php";
           
            $.ajax({
                url: URLs,
                data: $('#sentToBack').serialize(),
                type:"POST",
                dataType:'text',
                success: function(msg){
                    alert(msg);
                },
                 error:function(xhr, ajaxOptions, thrownError){ 
                    alert(xhr.status); 
                    alert(thrownError); 
                 }
            });
        }
</script>
```
ajax當中的參數：
-url：指定要進行呼叫的位址。

-data：傳送至Server的資料，會自動轉為query string的型式，如果是GET請求還會幫你附加到URL。可用processData選項禁止此自動轉換。
      物件型式則為一Key/Value pairs。這個範例程式，是使用serialize()，會把name為sentToBack的表單中的資料傳送出去，型態的部分要看type的設定，
      一般表單都是用POST或是GET。
      
-type：請求方式，POST/GET。

-dataType：預期Server傳回的資料類型，如果沒指定，jQuery會根據HTTP MIME Type自動選擇以responseXML或responseText傳入你的success callback。
          可選的資料類型有：
                  xml：傳回可用jQuery處理的XML
                  html：傳回HTML，包含jQuery會自動幫你處理的script tags。
                  script：傳回可執行的JavaScript。(script不會被自動cache，除非cache設為true)
                  json：傳回JSON
                  jsonp：在URL加上?callback=?參數，並在Server端配合送回此jsonp callback。
                  text：傳回純文字字串。
                  
-success：請求成功時執行函式。
                function (data, textStatus) {
                       // data 可以是 xmlDoc, jsonObj, html, text, 但還是要參考datatype                          
                } 
                
-error：請求失敗時執行函式。
           function (xhr, ajaxOptions, thrownError) {
                   //通常ajaxOptions或thrownError只有一個有值
           } 
           這個很重要，因為有時候Sever寫好的程式不容易測試，可以透過這個函數把錯誤顯示出來。
          
          
其他可能比較會用的參數：
-complete：請求完成時執行的函式(不論結果是success或error)。
                 function (XMLHttpRequest, textStatus) {
                   // the options for this ajax request 
                 }
                 
-beforeSend：發送請求之前可在此修改XMLHttpRequest物件，如添加header等，你可以在此函式中return flase取消Ajax request。
                     function (XMLHttpRequest) { 
                          // the options for this ajax request 
                     }
                     
      
      
***
>參考網站:
- Ajax的基本運用 <http://expect7.pixnet.net/blog/post/37919326-%5B%E7%A8%8B%E5%BC%8F%5D%5Bjquery%5D-jquery%E4%B8%AD%E7%9A%84ajax%E7%9A%84%E5%9F%BA%E7%A4%8E%E9%81%8B%E7%94%A8%E3%80%82%E6%8F%90%E4%BE%9B%E7%AF%84>               
