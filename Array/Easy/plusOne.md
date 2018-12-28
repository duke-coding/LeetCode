# 题目

给定一个由**整数**组成的**非空**数组所表示的非负整数，在该数的基础上加一。

最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。

你可以假设除了整数 0 之外，这个整数不会以零开头。

**示例 1**

```
输入: [1,2,3]
输出: [1,2,4]
解释: 输入数组表示数字 123。
```

**示例 2**

```
输入: [4,3,2,1]
输出: [4,3,2,2]
解释: 输入数组表示数字 4321。
```



# 思路

首先考虑边界情况，如果是x9这种形式，位数会增加一位，所以要考虑这种情况。

考虑数字位数大于2的32次方，如何处理大数的相加。

因此可以简单粗暴直接用java.math.BigInteger，也可以考虑使用栈,stack.

```java
class Solution_e {
    public int[] plusOne(int[] digits) {
        
        return digits;
    }

    public static void main(String[] args) {
        int[] nums = new int[]{9,9,9,9,9,9,9,9,9,9,9};
        Solution_e run = new Solution_e();
        int[] result = run.plusOne(nums);
        for(int num : result){
            System.out.println(num);
        }

    }
}
```

Beats % 