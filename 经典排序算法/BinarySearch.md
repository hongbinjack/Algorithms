```java
package hongbinAlgorithm;

import java.util.Scanner;

public class BinarySearch {
   public static int binarySearch(int[] arr,int target){
      int left = 0,right = arr.length-1;

        while(left <= right){
             int middle = left + (right - left)/2;
         if(target == arr[middle]){
            return middle;
         } else if (arr[middle] > target) {
            right = middle - 1;
         } else if (arr[middle] < target) {
            left = middle + 1;
         }
      }

      return -1;
   }

   public static void main(String[] args) {
      int[] arr={1,3,45,56,67,333,666,977,6565,8565,8999};
      System.out.println("请输入一个整数：");
      Scanner sc=new Scanner(System.in);
      int target=sc.nextInt();
      int result = binarySearch(arr,target);
      System.out.println("数组中存在该整数，它在数组中的索引是：" + result);
   }
}
```
