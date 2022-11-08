```java
package hongbinAlgorithm;

import java.util.Arrays;

public class BubbleSort {

    public static void bubbleSort_m2(int[] arr){
       int n = arr.length - 1;
       int num = 1;
       while(true){
           int last = 0;//表示最后一次交换索引的位置
           for(int i = 0;i<n;i++){
               System.out.println("比较次数"+i);
               if(arr[i] > arr[i+1]){
                   int temp=arr[i+1];
                   arr[i+1] = arr[i];
                   arr[i] = temp;
                   last=i;
               }
           }
           n = last;
           System.out.println("第"+ num++ +"次"+"冒泡:" + Arrays.toString(arr));
           if(n == 0){
               break;
           }
       }
    }
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
                System.out.println("比较次数："+ (j+1));
            }
            System.out.println("第"+i+"轮冒泡：" + Arrays.toString(arr));
            if(flag){
                break;
            }
        }
    }
    public static void main(String[] args) {
        int[] arr = {1,22,32,4,52,55,77,82,99};
//        bubbleSort(arr);
        System.out.println("----------------");
        bubbleSort_m2(arr);
    }
}



```
