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

首先考虑边界情况，如果是xxx9这种形式，位数会增加一位，所以要考虑这种情况。

因此可以简单粗暴直接用java.math.BigInteger，但是比较好的还是数组复制.

```java
class Solution_e {
    public int[] plusOne(int[] digits) {
        int add = 1;
        for (int i = digits.length - 1; i >= 0; i--) {
            if (digits[i] + add == 10) {
                digits[i] = 0;
            }else {
                digits[i] += add;
                return digits;
            }
        }
        int[] ansArr = new int[digits.length + 1];
        ansArr[0] = 1;
        System.arraycopy(digits, 0, ansArr, 1, ansArr.length - 1);
        return ansArr;
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

Beats 51% 