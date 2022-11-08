```java
package hongbinAlgorithm;

import java.util.Arrays;

public class BubbleSort {
     public static  void bubbleSort(int[] arr){

         for(int i=1;i<arr.length;i++){
             boolean flag = true;
             for(int j=0;j<arr.length -i;j++){
                 if(arr[j] > arr[j+1]){
                     int temp=arr[j+1];
                         arr[j+1] = arr[j];
                         arr[j] = temp;
                     flag = false;
                 }
                 System.out.println("第"+(j+1)+"次比较:" + Arrays.toString(arr));
             }
             System.out.println("第"+i+"轮冒泡：" + Arrays.toString(arr));
             if(flag){
                 break;
             }
         }
     }
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,55,7,8,9};
        bubbleSort(arr);

    }
}


```
