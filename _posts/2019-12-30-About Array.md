#### 原数组被改变
```js
array.splice(start, deleteCount, items1,items2....)
```
​	start: 从第 start 位开始( 负数为 倒数)
​	deleteCount: 删除的个数（为 0  或者 负数 则不删除）
​	items1,items2....  : 要插入的元素。

 ```js
 var arr=[12,13,14,16,15];
 arr.splice(2,0,19,12);  =>  return       [12,13,19,12,14,16,15]
 var removed = arr.splice(1,2) =>  return [13,19]
 ```


	* push() 向数组的末尾添加一个或更多元素，并返回新的长度。


​		arr.push("as",12)  => return [12,13,19,12,14,16,15,"as",12]

	* unshift() 向数组的开头添加一个或更多元素，并返回新的长度。

​		arr.unshift("as",12,15) => ["as",12,15,12,13,19,12,14,15,"as",12]


	* pop() 删除并返回数组的最后一个元素
	
	* shift() 删除并返回数组的第一个元素
	
	* reverse() 颠倒数组中元素的顺序
	
	* sort() 对数组的元素进行排序

方法用原地算法对数组的元素进行排序，并返回数组。默认排序顺序是在将元素转换为字符串，然后比较它们的UTF-16代码单元值序列时构建的
```js
var arr=[12,16,1,2,5,19,31]; arr.sort((a,b)=>{return a-b});    ==》升序   [1, 2, 5, 12, 16, 19, 31]
arr.sort((a,b)=>{return b-a});  ==> 降序  [31, 19, 16, 12, 5, 2, 1]
```

##### Array from a String
```js
Array.from('foo');
// [ "f", "o", "o" ]
```
##### Array from a Set
```js
const set = new Set(['foo', 'bar', 'baz', 'foo']);
Array.from(set);
// [ "foo", "bar", "baz" ]
```
##### Array from a Map
```js
const map = new Map([[1, 2], [2, 4], [4, 8]]);
Array.from(map);
// [[1, 2], [2, 4], [4, 8]]

const mapper = new Map([['1', 'a'], ['2', 'b']]);
Array.from(mapper.values());
// ['a', 'b'];

Array.from(mapper.keys());
// ['1', '2'];

```