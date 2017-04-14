## 查找元素
 
 `getElementById`,`getElementByTagName`
 
 ### getElementById
在ie7及较低版本：name特性与给定ID匹配的表单与元素（`<input>`,`<textarea>`,`<button>`,`<select>`）也会被该方法返回。

```html
<input type="text" name="myElement" value="">
<div id="myElement"></div>
```
```javascript
var getElement = document.getElementById('myElement');
console.log('getElement',getElement);

//<input type="text" name="myElement" value=""> ie7及以下

//<div id="myElement"></div>   其他浏览器
```

### getElementByTagName

返回的是包含0个或者多个元素的NodeList

```javascript
console.log(document.getElementsByTagName('div'));
// [div#myElement, myElement: div#myElement]
// length:1
// myElement:div#myElement
// 0:div#myElement
// __proto__:HTMLCollection
```
    `namedItem()`方法通过元素的name特性取得集合中的项
    
```html
<input type="text" name="myElement" value="">
```
```javascript
var divElement = document.getElementsByTagName('input');
console.log(divElement.namedItem('myElement'));

// var divElement = document.getElementsByTagName('input');
```
