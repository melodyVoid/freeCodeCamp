# 2018-04-12

## 1.反转字符串

```js
// 反转字符串
function reverseString(str) {
  return str.split('').reverse().join('');
}

reverseString("hello");
```

## 2.求阶乘

```js
// 求阶乘
function factorialize(num) {
  if (num === 0) return 1;
  return num * factorializa(num - 1);
}
factorialize(5);
```

## 3.判断字符串是否回文

```js
// 回文
function palindrome(str) {
  // Good luck!
  var format = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();
  return format.split('').reverse().join('') === format;
}

palindrome("A man, a plan, a canal. Panama");

```

## 4.找出一句英文中字母最长的单词的长度

```js
// 找出一句英文中字母最长的单词的长度
function findLongestWord(str) {
  const arr = str.split(' ').map(item => item.length);
  return Math.max(...arr);
}

findLongestWord("The quick brown fox jumped over the lazy dog");
```

```js
function findLongestWord(str) {
  str = str.split(' ').reduce((pre, cur) => pre.length > cur.length ? pre : cur);
  return str.length;
}

findLongestWord("The quick brown fox jumped over the lazy dog");

```

## 5. 英文句子的首字母大写

```js
// 英文句子的首字母大写
function titleCase(str) {
  return str.toLowerCase().split(' ').map(item => item[0].toUpperCase() + item.slice(1)).join(' ');
}

titleCase("I'm a little tea pot");
```

# 2018-04-13

## 6.返回二维数组中每一个数组中的最大值为一个新数组

```js
// 返回二维数组中每一个数组中的最大值为一个新数组
function largestOfFour(arr) {
  return arr.map(item => Math.max(...item));
}

largestOfFour([[4, 5, 1, 3], [13, 27, 18, 26], [32, 35, 37, 39], [1000, 1001, 857, 1]]);
```

## 7. 用 ES5 的方式实现 ES6 的 `.endsWith()`

```js
// 用 ES5 的方式实现 ES6 的 .endsWith()
function confirmEnding(str, target) {
  return str.substr(-target.length) === target;
}

confirmEnding("Bastian", "n");
```

## 8.repeat 字符串

```js
// repeat 字符串
function repeatStringNumTimes(str, num) {
  if (num <= 0) return '';  // num 为 0 或负数时也要考虑到
  return str.repeat(num);
}

repeatStringNumTimes("abc", 3);
```

## 9. 缩短字符串，如果字符串的长度大于第二个参数num，返回缩短后的字符串（以 … 结尾）；如果给定的最大字符串长度小于或等于3，则在确定缩短字符串时，添加三个点不会增加字符串长度。

```js
// 测试用例
truncateString("A-tisket a-tasket A green and yellow basket", 11)
should return "A-tisket...".

truncateString("Peter Piper picked a peck of pickled peppers", 14) 
should return "Peter Piper...".

truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length) 
should return "A-tisket a-tasket A green and yellow basket".

truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2) 
should return "A-tisket a-tasket A green and yellow basket".

truncateString("A-", 1) 
should return "A...".

truncateString("Absolutely Longer", 2) 
should return "Ab...".
```

```js
//  缩短字符串，如果字符串的长度大于第二个参数num，返回缩短后的字符串（以 … 结尾）；如果给定的最大字符串长度小于或等于3，则在确定缩短字符串时，添加三个点不会增加字符串长度。
function truncateString(str, num) {
  const strLength = str.length;
  if (strLength > num) {
    return str.substr(0, num > 3 ? num -3 : num) + '...';
  } else {
    return num > 3 ? str : str.substr(0, num) + '...';
  }
}

truncateString("Absolutely Longer", 2);
```

## 10. 按照给定的`size`将一个数组切分成含有`size`个数的更小数组块的数组

```js
// 按照给定的size将一个数组切分成含有size个数的更小数组块的数组
function chunkArrayInGroups(arr, size) {
 return Array.from({ length: Math.ceil(arr.length / size)}, (item, index) => {
   return arr.slice(index * size, index * size + size);
 });
}

chunkArrayInGroups(["a", "b", "c", "d"], 2);
```



