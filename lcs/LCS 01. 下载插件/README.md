# [LCS 01. 下载插件](https://leetcode-cn.com/problems/Ju9Xwi/)

## 题目描述

<!-- 这里写题目描述 -->

小扣打算给自己的 **VS code** 安装使用插件，初始状态下带宽每分钟可以完成 `1` 个插件的下载。假定每分钟选择以下两种策略之一:

-   使用当前带宽下载插件
-   将带宽加倍（下载插件数量随之加倍）

请返回小扣完成下载 `n` 个插件最少需要多少分钟。

注意：实际的下载的插件数量可以超过 `n` 个

**示例 1：**

> 输入：`n = 2`
>
> 输出：`2`
>
> 解释：
> 以下两个方案，都能实现 2 分钟内下载 2 个插件
>
> -   方案一：第一分钟带宽加倍，带宽可每分钟下载 2 个插件；第二分钟下载 2 个插件
> -   方案二：第一分钟下载 1 个插件，第二分钟下载 1 个插件

**示例 2：**

> 输入：`n = 4`
>
> 输出：`3`
>
> 解释：
> 最少需要 3 分钟可完成 4 个插件的下载，以下是其中一种方案:
> 第一分钟带宽加倍，带宽可每分钟下载 2 个插件;
> 第二分钟下载 2 个插件;
> 第三分钟下载 2 个插件。

**提示：**

-   `1 <= n <= 10^5`

## 解法

<!-- 这里可写通用的实现逻辑 -->

如果不能在一分钟内下载完，那么可以先加速，循环直至能在一分钟内下载完。那么“循环次数 + 1”即为最少消耗的分钟数。

<!-- tabs:start -->

### **Python3**

<!-- 这里可写当前语言的特殊实现逻辑 -->

```python
class Solution:
    def leastMinutes(self, n: int) -> int:
        speed = res = 1
        while speed < n:
            speed <<= 1
            res += 1
        return res
```

### **Java**

<!-- 这里可写当前语言的特殊实现逻辑 -->

```java
class Solution {
    public int leastMinutes(int n) {
        int speed = 1;
        int res = 1;
        while (speed < n) {
            speed <<= 1;
            ++res;
        }
        return res;
    }
}
```

### **C++**

```cpp
class Solution {
public:
    int leastMinutes(int n) {
        int speed = 1, res = 1;
        while (speed < n)
        {
            speed <<= 1;
            ++res;
        }
        return res;
    }
};
```

### **Go**

```go
func leastMinutes(n int) int {
	speed, res := 1, 1
	for speed < n {
		speed <<= 1
		res++
	}
	return res
}
```

### **...**

```

```

<!-- tabs:end -->
