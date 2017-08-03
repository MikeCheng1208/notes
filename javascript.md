document.querySelectorAll("") 回傳的Array無法使用forEach或是map等方法，因回傳陣列繼承的東西不一樣，所以不能用

要可以使用的話方法有兩個，其一是利用取出陣列的length然後跑for迴圈來取出val，另外一個是是擷取陣列方法使用.call使用它
```js
/*
    document.querySelectorAll(".el") 回傳是
    [
        0: <li class="el">文本一<li>,
        1: <li class="el">文本二<li>,
        2: <li class="el">文本三<li>,
        3: <li class="el">文本四<li>
    ]
*/
var forEach = Array.prototype.forEach
var items = document.querySelectorAll(".el")
forEach.call(items,function(item){
    console.log(item)
})
```
---
### 使用document.querySelectorAll 跟 document.getElementsByClassName的差別
Html
```html
<ul id="el">
    <li class="feature">1</li>
    <li class="feature">2</li>
    <li class="feature">3</li>
</ul>
```
JavaScript
- 使用 querySelectorAll -> 返回的是一個靜態結果
```js
    var item = document.querySelectorAll(".feature")
    console.log(item.length)
    //回傳 -> 3

    var ulSelect = document.querySelector("#el")
    var liCreate = document.createElement("li")
    liCreate.className = "feature"
    liCreate.innerText = "4"
    ulSelect.appendChild(liCreate)
    /*
        <ul id="el">
            <li class="feature">1</li>
            <li class="feature">2</li>
            <li class="feature">3</li>
            <li class="feature">4</li>
        </ul>
    */
    console.log(item.length)
    //回傳 -> 3
```
- 使用 getElementsByClassName -> 返回的是現場的結果
```js
    var item = document.getElementsByClassName("feature")
    console.log(item.length)
    //回傳 -> 3

    var ulSelect = document.querySelector("#el")
    var liCreate = document.createElement("li")
    liCreate.className = "feature"
    liCreate.innerText = "4"
    ulSelect.appendChild(liCreate)

    /*
        <ul id="el">
            <li class="feature">1</li>
            <li class="feature">2</li>
            <li class="feature">3</li>
            <li class="feature">4</li>
        </ul>
    */
    console.log(item.length)
    //回傳 -> 4
```

---
### input oninvalid & onblur 
```html
<input type="text" id="form-input" required>
```
```js
document.getElementById('form-input').oninvalid = function(){
    // 提交的input元素的值為無效值時，觸發oninvalid事件。
    // input元素設置了required屬性，但是提交時該處為空就會觸發oninvalid事件
}
document.getElementById('form-input').onblur = function(){
    // 使用 onblur 事件在用戶離開 input 時執行function
}
```

---
