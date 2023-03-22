```java
package hongbinAlgorithm;

import java.util.Arrays;

public class SelectionSort {
    public static void selectSort(int[] arr){
        for(int i=0;i<arr.length-1;i++){
            int minIndex = i;
            for(int j=i+1;j<arr.length;j++){  //不要等于号否则会抛出索引越界异常
                if(arr[j] < arr[minIndex]){   //i改成minIndex，否则排序不准确
                    minIndex = j;
                }
            }
            if(minIndex != i){
                int tem = arr[i];
                arr[i] = arr[minIndex];
                arr[minIndex] = tem;
            }
        }
    }

    public static void main(String[] args) {
        int[] arr={2,5,6,4,45,78,333,768,976,335,313,575};
        SelectionSort.selectSort(arr);
        System.out.println(Arrays.toString(arr));
    }
}

```
