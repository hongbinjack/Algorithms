```java
package hongbinAlgorithm;

import java.util.Arrays;

public class InsertSort {
    public static void insertSort(int[] arr){

        for(int i=1;i<arr.length;i++){
            int temp = arr[i];
            int j = i-1;
            while(j >= 0){
                if(temp < arr[j]){
                    arr[j+1] = arr[j];
                }else {
                    break;
                }
                j--;
            }
            arr[j+1] = temp;
        }
        System.out.println(Arrays.toString(arr));
    }

    public static void main(String[] args) {
        int[]  arr={2,45,64,46,77,43,78,96,93,99,333,675,555,775};
        insertSort(arr);
    }
}

```

- 最好时间复杂度：O(n)
- 最坏时间复杂度：O(n^2)
- 空间复杂度：O(1)
