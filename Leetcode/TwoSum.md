```java


package LeetCode;

import java.util.Arrays;


public class TwoSum {
    public static int[] twoSum(int[] nums, int target) {
        int n = nums.length;
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j < n; ++j) {
                if (nums[i] + nums[j] == target) {
                    return new int[]{i, j};
                }
            }
        }
        return new int[0];
    }

    public static int[] twoSumT(int[] arr,int target){
     int left = 0,right = arr.length-1;
     if(arr.length == 0)  return null;
        while (left != right) {
            int sum = arr[left] + arr[right];
            if (sum < target) {
                left++;
            } else if (sum > target) {
                right--;
            } else if (sum == target) {
                return new int[]{left, right};
            }
        }
        return null;
    }
    public static void main(String[] args) {
        int[] arr = {3,4,56,78,8,3,5,9};
        System.out.println("在数组中对应的索引(索引从0开始):"+Arrays.toString(twoSum(arr,66)));
        System.out.println("在数组中对应的索引(索引从0开始):"+Arrays.toString(twoSumT(arr,7)));
    }

}
```

**解法TwoSum**：暴力解法

- 时间复杂度：O(N^2)，其中 N 是数组中的元素数量。最坏情况下数组中任意两个数都要被匹配一次。
- 空间复杂度：O(1)



**解法TwoSumT**：双指针解法

- 数组中的元素最多遍历一次，时间复杂度为 O(N)。
- 只使用了两个额外变量，空间复杂度为 O(1)。




``
