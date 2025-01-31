# Utils
导入
````js
  import { Utils } from '@dtinsight/dt-utils';
````

## browserCheck
浏览器类型和版本检测

`true`表示通过兼容性检测,`false`表示不通过兼容性检测

```js
  Utils.browserCheck(); // boolean 
```
## checkExist
检查属性是否存在
```js
  Utils.checkExist()
```
例如:
```js
  Utils.checkExist('') // false
  Utils.checkExist(null) // false
  Utils.checkExist(undefined) // false
```
## isMacOs
判断设备是否是Mac
```js
  Utils.isMacOs(); //boolean
```
## isWindows
判断设备是否是Windows
```js
  Utils.isWindows(); //boolean
```
## isMobileDevice
判断设备是否是移动设备
```js
  Utils.isMobileDevice(); //boolean
```
## isPhoneNumber
判断是否是手机号
````js

Utils.isPhoneNumber('15688723782333') // false

````
## isJSONStr
判断是否是JSON string
```js
Utils.isJSONStr (str: string): boolean
```
例如:
```js
Utils.isJSONStr('name') // false
```
## isFunction
判断是否是函数
````js

Utils.isFunction([]) // false
Utils.isFunction(()=>{}) // true

````
## isEqualArr
简单地判断数组是否相等
```js
Utils.isEqualArr (arr1: any[], arr2: any[]): boolean
```
例如:
```js
Utils.isEqualArr([1,2,3], [1,2,3]) // true
Utils.isEqualArr([1,2,3],[1,3,2]) // true
```

## isEqual
简单地判断对象是否相等
```js
Utils.isEqual (a: any, b: any): boolean
```
例如:
```js
Utils.isEqual({name:'sichen'},{name:'sichen'}) // true
```
## getParameterByName
根据参数名获取URL数据

```js
 /**
   * 获取图片的Base64格式
   *  @param  {[type]} name [description]
   * @param  {[type]} url  [description] 可选参数，默认当前域
   */
  Utils.getParameterByName(); //boolean 
```

例如:
```js
  Utils.getParameterByName('name','http://baidu.com?name='1'); // 1 
  Utils.getParameterByName('name'); // 1 
```
## getBase64
获取图片的Base64格式

```js
  /**
   * 获取图片的Base64格式
   * @param  {[type]}   img      [description]
   * @param  {Function} callback [description]
   */
  Utils.getBase64(img,callback); 
```
## getCssText
  样式对象转css style风格转字符串

````js
/**
 * @param {Record<string, any>} [object={}]
 * @returns String
 */
  Utils.getCssText(object: Record<string, any> = {}); 
````
例如:

````js
  let styles = {
    height:'100px',
    width:'100px',
    color:'red'
  }
  Utils.getCssText(styles); // 'height:100px;width:100px;color:red;'
````
## generateAKey
生成一个随机key

例如:
```js
Utils.generateAKey(): string // "1594806665598655835"
```


## getRandomStr
随机生成一串len位同时包含数字、大小写字母的字符串
```js
    Utils.getRandomStr (len: number): string
```
例如:
```js
Utils.getRandomStr(10) // "5vK6vT6sL8"
```
## getStrlen
计算字符串长度(英文占1个字符，中文汉字占2个字符)

```` js
 /**
     *
     * 计算字符串长度(英文占1个字符，中文汉字占2个字符)
     * @param {*} str
     * @returns number
     */
    Utils.getStrlen('上岁数1232');//10

````
## trim
去除前后空格
```js
    /**
    * @returns string
    */
    Utils.trim (str: string)
```
例如:
```js
Utils.trim(' 12 3 1    23  ') // "12 3 1    23"
```
## trimAll
去除所有空格
```js
    /**
    * @returns string
    */
    Utils.trimAll (str: string)
```
例如:
```js
Utils.trimAll(' 12 3 1    23  ') // "123123"
```
## toQfw
千位分割
```js
Utils.toQfw (str: string): string
```
例如:
```js
Utils.toQfw('123123') // "123,123"
```

## textOverflowExchange
文字溢出转换
```js
Utils.textOverflowExchange (str: string, num: number): string
```
例如:
```js
Utils.textOverflowExchange('my name is sichen', 10) // "my name is..."
```

## percent
百分比转换

````js
   /**
   * @param  {[type]} num       [description]
   * @param  {[type]} precision [description]
   */
  Utils.percent(num: number, precision?: number); 
````
例如:

````js
 Utils.percent(1); // 100%
 Utils.percent(0.5); // 50%
 Utils.percent(0.54); // 54%
 Utils.percent(0.54321); // 54.32%
 Utils.percent(0.54321,1); // 54.3%
 Utils.percent(0.54321,2); // 54.32%
 Utils.percent(0.54321,3); // 54.321%
````

## convertBytes
转换 Byte 转换为小于1024值最大单位
```js
Utils.convertBytes (value: number): string
```
例如:
```js
Utils.convertBytes(102) // 102 B
Utils.convertBytes(1024) // 1 KB
Utils.convertBytes(1024*1024) // 1 MB
```
## jsonFormat
json格式化

```js
// 格式化内容: text
// 格式化占位符: space
Utils.jsonFormat (text: string, space?: number)
```

## sortByCompareFunctions
多函数排序，匹配到0为止
```js
Utils.sortByCompareFunctions (arr: any[], ...compareFunctions: any[])
```

## exchangeOrder
转换排序字段
```js
Utils.exchangeOrder (order: string): string {
    switch (order) {
        case 'ascend':
            return 'asc';
        case 'descend':
            return 'desc';
        default:
            return undefined;
    }
}
```
例如:
```js
Utils.exchangeOrder('ascend') // 'asc'
Utils.exchangeOrder('descend') // 'desc'
Utils.exchangeOrder('abc') // undefined
```


## shouldRender
```js
Utils.shouldRender (targetComponent: any):boolean
```
## transformArray
一维数组根据指定位数转换成二维数组
```js
Utils.transformArray<T> (arr: T[], num: number): T[][]
```
例如:
```js
Utils.transformArray(['1', '2', '3', '4'], 2) // [['1', '2'], ['3', '4']]
```
## isEmpty
判空
```js
Utils.isEmpty (data?: any): boolean
```
例如:
```js
Utils.isEmpty('') // true
Utils.isEmpty(null) // true
Utils.isEmpty(undefined) // true
Utils.isEmpty([]) // true
Utils.isEmpty({}) // true
Utils.isEmpty('123') // false
```
## isObj
判断是否为对象
```js
Utils.isObj (obj?: any): boolean
```
例如:
```js
Utils.isObj({}) // true
Utils.isObj('123') // false
```
## removeEmpty
剔除对象中value为'',null,undefined,[]的元素
```js
Utils.removeEmpty (obj?: any): any
```
例如:
```js
Utils.removeEmpty({ a: 'test', b: undefined, c: { d: undefined } }) // { a: 'test', c: {} }
```

## mergeDeep

将两个对象进行深拷贝合并，对象内的同名对象也进行一次深拷贝合并  
如果 obj2 存在 _isMergeAtom 属性，则直接使用 obj2，不再与 obj1 合并

```js
mergeDeep(
    { a: 123, b: 321, innerObj: { a: 123, c: 456 } },
    { a: 'cover', c: 456, innerObj: { a: 'cover', b: 321 } }
)
// { a: 'cover', b: 321, c: 456, innerObj: { a: 'cover', b: 321, c: 456 } }
```
