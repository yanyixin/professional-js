提供了对元素标签名、子节点及特性的访问

### nodeName , tagName
访问元素的标签名
```html
<div id="myDiv"></div>
```
```javascript
console.log('tagName:',div.tagName,'nodeName:',div.nodeName);
// tagName: DIV nodeName: DIV
```
在html中，标签名始终都以**全部大写**表示。

## HTML元素

所有html元素都由HTMLElement类型表示。
- dir，语言的方向，“ltr”：left-to-right
- lang，元素内容的语言代码

```javascript
console.log('div.id:',div.id); // div.id: myDiv
```

也可以为每个属性赋予新的值

```javascript
div.id = 'someOtherId';
```

### 取得特性 getAttribute()

```javascript
console.log(div.getAttribute('id')); // myDiv
```
根据HTML5规范，自定义特性前面应该加上`data-`前缀以便验证。
```html
<div id="myDiv" data-my-name="div-name"></div>
```
```javascript
console.log(div.getAttribute('data-my-name')); // div-name
```
### 设置特性 setAttribute()

接受两个参数：要设置的特性名、值

    如果特性不存在，则创建该属性并且设置相应的值
    
```javascript
div.setAttribute('class','div-class');
```
```html
<div id="myDiv" data-my-name="div-name" class="div-class"></div>
```
### 删除特性 removeAttribute( )

彻底删除元素的特性
```javascript
div.removeAttribute('id');
```

### attribute 属性
