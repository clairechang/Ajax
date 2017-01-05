#JQuery
jQuery 是一套物件導向式簡潔輕量級的 JavaScript Library。透過 jQuery 你可以用最精簡少量的程式碼來輕鬆達到跨瀏覽器 DOM 操作、事件處理、設計頁面元素動態效果、AJAX 互動等。

####如何使用 jQuery

到網站 http://jquery.com/download/  下載 jQuery Library 
```html
接著將此 JS 檔放進你網頁 HTML 的 <head> 及 </head> 之間
<script src="你的 jQuery 檔案路徑"></script>

<head>
<script src="jquery-3.1.1.min.js"></script>
</head>
```
或者透過 Google CDN 或 Microsoft CDN 載入 jQuery (好處：免費、快)
```html
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script src="https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.1.1.min.js"></script>
```
#### jQuery Syntax
```html
Basic syntax is: $(selector).action()
Examples:
$(this).hide() - hides the current element.
$("p").hide() - hides all <p> elements.
$(".test").hide() - hides all elements with class="test".
$("#test").hide() - hides the element with id="test".

$(document).ready(function(){

   // jQuery methods go here...

});

$(function(){

   // jQuery methods go here...

});

Examples:
<script>
$(document).ready(function(){
    $("button").click(function(){
        $("p").hide();
    });
});
</script>

```
