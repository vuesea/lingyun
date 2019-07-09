## 001 - 两数之和 (two-sum)

### 一 感慨

------

心血来潮,准备跟随大佬的步伐,刷LeetCode,看到第一个题目,就呆住了!我靠怎么可以这么难.原来自己水平好水呀-----立志学好 算法和数据结构 .

### 二 学习方法

------

跟随jsliang的脚步一天一个坑,日积月累,培养自己学习能力.

### 三 考察知识点和题目

------

```
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。

示例:

给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```

### 四 解题

------

#### 4.1 解法 - for()

- 解题代码

  ```
  var twoSum = function(nums, target) {
    for (let i = 0; i < nums.length; i++) {
      for (let j = i + 1; j < nums.length; j++) {
        if (nums[j] === target - nums[i]) {
          return [i, j];
        }
      }
    }
  };
  ```

- 执行测试:
  1. nums: [1,3,2,5,6]
  2. target: 8
  3. return: 

- 解题思路 : 使用双重for循环 暴力破解

  ![](H:\assign\images\img\other-algorithm-001-1.png)

  1. 第一遍过滤 `nums` 数组，标记为 `i`。
  2. 第二遍再次过滤 `nums` 数组，标记为 `i + 1`，因为我们是对数组中的两个数字相加，所以不能重复使用同一个数字。
  3. 判断第二次遍历的数字中，它是否等于 `target - nums[i]`，如果成立就返回两个数字的索引。（并不考虑后面还有可成立的答案）。

#### 4.2  解法  - indexOf()

+ 解题代码

  ```
  var twoSum = function(nums, target) {
    let result = [];
    nums.map((item, index) => {
      if (nums.indexOf(target - item) > -1 && nums.indexOf(target - item) != index) {
        result = [index, nums.indexOf(target - item)].sort((a, b) => a > b);
      }
    });
    return result;
  };
  ```

+ 执行测试:

  1. nums: [4,3,2,5,6]

  2. target:8

  3. return:

     ```
     [2, 4]
     ```

+ 知识点:

  1. `map()`：遍历数组，`item` 返回遍历项，`index` 返回当前索引。
  2. `indexOf()`：判断数组中是否存在判断条件中的值。如果存在，则返回第一次出现的索引；如果不存在，则返回 -1。
  3. 排序，保持返回数组的数字为顺序排列。

+ 解题思路

  ![](H:\assign\images\img\other-algorithm-001-3.png)

  **首先**，我们开辟一块内存 `result`。

  **然后**，我们通过 `map()` 遍历 `nums`，并使用 `indexOf()` 寻找除当前 `item` 的 `index` 之外和 `item` 相加之和为 `target` 的结果。

  **最后**，我们返回查找的最新结果，该结果进行了排序（`[4, 2]` 的返回通过 `sort()` 排序变成 `[2, 4]`）

  **例如**，在上面测试 `twoSum([1, 3, 2, 5, 6], 8)` 的结果就有：

  ```
  [1, 3]
  [2, 4]
  [3, 1]
  [4, 2]
  ```

  我们取最后一次的结果并排序返回，即：`[2, 4]`

  - **进一步思考**：如果我们将 `map()` 换成 `for()`，你知道该如何操作么？

#### 4.3 解法 - Map

- **解题代码**：

```
var twoSum = function(nums, target) {
  let map = new Map();
  for (let i = 0; i < nums.length; i++) {
    if (map.has(nums[i])) {
      return [map.get(nums[i]), i];
    } else {
      map.set(target - nums[i], i);
    }
  }
};
```

- **执行测试**：

1. `nums`：`[4, 3, 2, 5, 6]`
2. `target`: `8`
3. `return`：

```
[1, 3]
```

- **知识点**：

1. `Map`：保存键值对。任何值(对象或者原始值) 都可以作为一个键或一个值.

- **解题思路**：

[![图](https://github.com/LiangJunrong/document-library/raw/master/public-repertory/img/other-algorithm-001-3.png)](https://github.com/LiangJunrong/document-library/blob/master/public-repertory/img/other-algorithm-001-3.png)

**首先**，我们需要了解 `Map` 这个对象。

1. 它可以通过 `set()` 的形式，以 `[key, value]` 的形式保存一组数据。（题目中对应 `key` 就是存入的 `target - nums[i]` 值，`value` 就是索引）
2. 它可以通过 `get()` 的形式，获取到传入 `key` 值对应的 `value`。
3. 它可以通过 `has()` 的形式，判断 `Map` 对象里面是否存储了传入 `key` 对应的 `value`。

**然后**，我们遍历 `nums` 数组。

**最后**，我们判断 `nums[i]` 是否存在于 `Map` 对象中。没有的话，就存入 `target - nums[i]` 到 `Map` 中。有的话，因为上次存入的是 `target- nums[i]`，有点类似于解题的钥匙，既然我们看到 `nums[i]` 存在于 `Map` 中，它是解题的钥匙，所以我们只需要返回 `[map.get(nums[i]), i]` 这组值即可。

### 五  拿来主义

------

以上解法均来自jsliang大佬目前，自己水平太过小白[链接](https://github.com/LiangJunrong/document-library/blob/master/other-library/LeetCode/easy/001-%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C%EF%BC%88two-sum%EF%BC%89.md)

