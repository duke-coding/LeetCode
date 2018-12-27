# 题目

给定一个整数数组 nums ，找到一个具有最大和的连续子数组（子数组最少包含一个元素），返回其最大和。

**示例 1**

```
输入: [-2,1,-3,4,-1,2,1,-5,4],
输出: 6
解释: 连续子数组 [4,-1,2,1] 的和最大，为 6。
```



# 思路

首先考虑边界情况，如果只有一个值，直接返回结果。

如果前面连续几项为负或者为0，就不用考虑累加，将下一项赋值即可,直至累积和大于0为止。当累积和大于最大和，赋值。

```java
class Solution_d {
    public int maxSubArray(int[] nums) {
        int Max = nums[0];
        int sum = 0;
        for(int i=0; i<nums.length;i++){
            if(sum<=0){
                sum = nums[i];
            }else{
                sum += nums[i];
            }
            if(sum>Max){
                Max = sum;
            }
        }
        return Max;
    }

    public static void main(String[] args) {
        int[] nums = new int[]{-2,1,-3,4,-1,2,1,-5,4};
        Solution_d run = new Solution_d();
        int result = run.maxSubArray(nums);
        System.out.println(result);

    }
}
```

Beats 99.83% 