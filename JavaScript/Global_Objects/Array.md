# Array

- [/docs/Web/JavaScript/Reference/Global_Objects/Array][Array]

[Array]: <https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array>


## 构造器 Constructor

- `Array()`
  - `Array.prototype.constructor()`
  - 创建 [Array] 对象

## 静态属性 Static properties

- `Array.lenght`
  - `Array.prototype.constructor.length`
  - [Array] 构造函数的 `lenght` 属性，即构造函数的参数个数，其值为 `1`

- `get Array[@@species]`
  - `Array[Symbol.species]`
  - 此访问器属性返回 [Array] 的默认构造函数

## 静态方法 Static methods

- `Array.from()`
- `Array.isArray()`
- `Array.of()`

## 实例属性 Instance properties

- `Array.prototype.constructor`
  - 构造器函数
  - 指定创建对象原型的函数
- `Array.prototype.lenght`
  - 反应数组中元素的数量
  - `Array.prototype.length === 0`
- `Array.prototype[@@unscopables]`

## 实例方法 Instance methods

- 修改器方法 Mutator methods

  - `copyWithin()`
    - `Array.prototype.copyWithin()`
  - `fill()`
    - `Array.prototype.fill()`
  - `pop()`
    - `Array.prototype.pop()`
  - `push()`
    - `Array.prototype.push()`
  - `reverse()`
    - `Array.prototype.reverse()`
  - `shift()`
    - `Array.prototype.shift()`
  - `sort()`
    - `Array.prototype.sort()`
  - `splice()`
    - `Array.prototype.splice()`
  - `unshift()`
    - `Array.prototype.unshift()`

- 访问器方法 Accessor methods

  - `concat()`
    - `Array.prototype.concat()`
    - 返回一个由当前数组和其它若干个数组或者若干个非数组值组合而成的新数组
  - `includes()`
    - `Array.prototype.includes()`
    - 判断当前数组是否包含某指定的值，如果是返回 `true` 否则返回 `false`
  - `indexOf()`
    - `Array.prototype.indexOf()`
  - `join()`
    - `Array.prototype.join()`
    - 连接所有数组元素组成一个字符串
  - `lastIndexOf()`
    - `Array.prototype.lastIndexOf()`
  - `slice()`
    - `Array.prototype.slice()`
    - 抽取当前数组中的一段元素组合成一个新数组
  - `toString()`
    - `Array.prototype.toString()`
  - `toLocaleString()`
    - `Array.prototype.toLocaleString()`

- 迭代方法 Iteration methods

  - `entries()`
    - `Array.prototype.entries()`
  - `every()`
    - `Array.prototype.every()`
  - `filter()`
    - `Array.prototype.filter()`
  - `find()`
    - `Array.prototype.find()`
  - `findIndex()`
    - `Array.prototype.findIndex()`
  - `forEach()`
    - `Array.prototype.forEach()`
  - `keys()`
    - `Array.prototype.keys()`
  - `map()`
    - `Array.prototype.map()`
  - `reduce()`
    - `Array.prototype.reduce()`
  - `reduceRight()`
    - `Array.prototype.reduceRight()`
  - `some()`
    - `Array.prototype.some()`
  - `values()`
    - `Array.prototype.values()`
    - 返回一个新的 `Array Iterator` 对象，该迭代器对象包含数组每个索引的值
    - [Examples >>](#ex-values)
  - `[@@iterator]()`
    - `Array.prototype[@@iterator]()`


---

## 示例 Examples


<h4 id="ex-values"><code>values()</code></h4>

```js
const iterator = ['a', 'b', 'c'].values()

for (const vlaue of iterator) {
  console.log(value)
}

// expected output: 'a' 'b' 'c'
```
