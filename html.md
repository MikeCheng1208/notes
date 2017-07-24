form 的 novalidate 屬性規定當提交表單時不對其進行驗證
```html
<form action="xxxxx.php" novalidate>
  <input type="email" />
  <input type="submit" />
</form>
```
---
input 的 required 屬性規定為必填
```html
<form action="xxxxx.php">
    <input required type="text">
    <input type="submit" />
</form>
<!--
    必需屬性適用於以下 input 類型 ：
    text,
    search,
    url,
    telephone,
    email,
    password,
    date pickers,
    number,
    checkbox,
    radio,
    file
-->
```
---

input 可以搭配 datalist 標籤做出可以輸入跟下拉的表單

demo :  <https://codepen.io/MikeCheng1208/pen/QgPmMP?editors=1100>
```html
<input type="text" 
    id="direction-list"  
    list="direction-data"
    placeholder="下拉選擇或輸入選擇">
			
<datalist id="direction-data">
    <option value="Apple"></option>
    <option value="Banner"></option>
    <option value="Origin"></option>
    <option value="Qoo"></option>
</datalist>
```
---
### html5 拖曳屬性
可搭配JS拖曳api使用
```html
    <img draggable="true">
    <!--draggable屬性是指定這個元件是可以拖動的元件-->



```