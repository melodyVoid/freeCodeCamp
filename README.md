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