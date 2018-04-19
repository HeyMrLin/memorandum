### 拓展知识点

1. [Object.defineProperty()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)

   语法：

   ```javascript
   Object.defineProperty(obj, prop, descriptor)
   ```

   参数说明：

   > obj：必需。目标对象 
   >
   > prop：必需。需定义或修改的属性的名字
   >
   > descriptor：必需。目标属性所拥有的特性

   返回值：

   > 传入函数的对象。即第一个参数obj

   + 数据描述：

   当修改或定义对象的某个属性的时候，给这个属性添加一些特性：

   ```javascript
   var obj = {
       test:"hello"
   }
   //对象已有的属性添加特性描述
   Object.defineProperty(obj,"test",{
       configurable:true | false, // (是否可以删除目标属性或是否可以再次修改属性的特性（writable, configurable, enumerable）)
       enumerable:true | false, // 是否可枚举(使用for...in或Object.keys())
       value:任意类型的值,
       writable:true | false // 是否可写
   });
   //对象新添加的属性的特性描述
   Object.defineProperty(obj,"newKey",{
       configurable:true | false,
       enumerable:true | false,
       value:任意类型的值,
       writable:true | false
   });
   ```

   在默认情况下都为false，即：

   ```javascript
   Object.defineProperty(obj,"newKey",{
       // 默认下
   });
   ```

   + 存取器描述

   当使用存取器描述属性的特性的时候，允许设置以下特性属性：

   ```javascript
   var obj = {};
   Object.defineProperty(obj,"newKey",{
       get:function (){} | undefined,
       set:function (value){} | undefined
       configurable: true | false
       enumerable: true | false
   });
   ```

   ***注意：当使用了getter或setter方法，不允许使用writable和value这两个属性***

2. [console.log()](https://segmentfault.com/a/1190000000481884)

3. [ES5.1](http://lzw.me/pages/ecmascript/)

4. [nodejs](http://nodejs.cn/)


