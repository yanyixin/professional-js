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
### document.getElementsByTagName('*')
    取得文档中的所有元素
```javascript
console.log(document.getElementsByTagName('*'));
```
返回包含了整个页面中的所有元素（按照它们出现的先后顺序）

### document.getElementsByName( )

    返回带有给定name特性的所有元素，返回一个HTMLCollection
### document.implementation
    检测浏览器实现了DOM的哪些部分
    DOM1级只为`document.implementation`规定了一个方法，
    即`hasFeature()`,接受两个参数：要检测的DOM功能的名称、版本号
```javascript
document.implementation.hasFeature('XML','1.0')
// true
```

## 文档写入

### write( )
    原样写入
```javascript
document.write('<b>'+ (new Date()).toString() +'</b>');
```

使用`write()`动态的包含外部资源。

```javascript
document.write("<script type=\"text/javascript\" src=\"file.js\">" + "<\/script>");
```
    
### writeIn( )
    会在字符串的末尾添加一个换行符(\n)
    
如果在页面加载结束后再调用`document.write( )`，输出的内容会重写整个页面。
```javascript
window.onload = function() {
    document.write('hello');
}
```
