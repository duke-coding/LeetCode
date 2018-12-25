# 题目

给定一个整数的数组nums，返回相加为target的两个数字的索引值。

假设每次输入都只有一个答案，并且不会使用同一个元素两次。

**举例：**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

# 思路

使用HashMap进行遍历，利用target 和已知的遍历数。每放进HashMap一组数，就利用get()查找一次进行判断是否找到。

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer,Integer> map = new HashMap<>();
        for (int i = 0; i< nums.length; i++) {
            int flag = target - nums[i];
            if(map.containsKey(flag)){
                return new int[]{map.get(flag),i};
            }
            map.put(nums[i],i);
        }
        throw new IllegalArgumentException("No Solution!");
    }


    public static void main(String[] args){
        int[] nums = new int[]{5, 1, 4, 3};
        int target = 7;
        Solution run  = new Solution();
        int[] result = run.twoSum(nums,target);
        System.out.println(Arrays.toString(result));

    }
}
```

Beats 80.31%