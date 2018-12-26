# 题目

给定一个排序数组，你需要在**原地**删除重复出现的元素，使得每个元素只出现一次，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在**原地修改输入数组**并在使用 O(1) 额外空间的条件下完成。

**示例 1**

```
给定数组 nums = [1,1,2], 

函数应该返回新的长度 2, 并且原数组 nums 的前两个元素被修改为 1, 2。 

你不需要考虑数组中超出新长度后面的元素。
```

**示例 2**

```
给定 nums = [0,0,1,1,1,2,2,3,3,4],

函数应该返回新的长度 5, 并且原数组 nums 的前五个元素被修改为 0, 1, 2, 3, 4。

你不需要考虑数组中超出新长度后面的元素。
```

**说明**

```
// nums 是以“引用”方式传递的。也就是说，不对实参做任何拷贝
int len = removeDuplicates(nums);

// 在函数里修改输入数组对于调用者是可见的。
// 根据你的函数返回的长度, 它会打印出数组中该长度范围内的所有元素。
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```

# 思路

因为在排序后的数组进行变动，而不扩展空间，当然就想到了指针来解决这个问题.

```java

class Solution {

    public int removeDuplicates(int[] nums) {
        if(nums.length ==0) return 0;
        int point_A = 0;
        //因为在排序后的数组进行变动，而不扩展空间，当然就想到了指针来解决这个问题
        for(int point_B =1; point_B<nums.length; point_B++){
            if(nums[point_B] != nums[point_A]){
                point_A ++ ;
                nums[point_A] = nums[point_B];
            }
        }
        return point_A+1;
    }

    public static void main(String[] args){
        int[] nums = new int[]{1,1,3,3,4,5};
        Solution run  = new Solution();
        int result = run.removeDuplicates(nums);
        System.out.println(result);
        for (int num: nums
             ) {
            System.out.println(num);
        }

    }
}
```

Beats 69.12% 