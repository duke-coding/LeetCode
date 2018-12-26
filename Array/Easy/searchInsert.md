# 题目

给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。

你可以假设数组中无重复元素。

**示例 1**

```
输入: [1,3,5,6], 5
输出: 2
```

**示例 2**

```
输入: [1,3,5,6], 2
输出: 1
```

**示例 3**

```
输入: [1,3,5,6], 7
输出: 4
```

**示例 4**

```
输入: [1,3,5,6], 0
输出: 0
```



# 思路

因为是在数组中查找指定值，是个查找问题，当然就想到了二分法查找。

```java
class Solution_c {
    public int searchInsert(int[] nums, int target) {
        int flag = Arrays.binarySearch(nums,target);
        if(flag>=0){
            return flag;
        }else {
            return -flag - 1;
        }

    }


    public static void main(String[] args) {
        int[] nums = new int[]{1,3,5,6};
        int target = 2 ;
        Solution_c run = new Solution_c();
        int result = run.searchInsert(nums, target);
        System.out.println(result);

    }
}
```

Beats 69.12%  