```java
package chapter02;

/**
 * 1)数据的插入，删除，按照下表随机访问操作；
 * 2)数组中的数据是int类型的
 */
public class Array {
    //定义整型数组保存数据
    public int data[];
    //定义数组长度
    private int n;
    //定义实际个数
    private int count;

    //构造方法,定义数组大小
    public Array(int capacity){
        this.data=new int[capacity];
        this.n=capacity;
        this.count=0;//一开始一个属都没有所以为0
    }

    //根据索引，找到数据中的元素并返回
    public int find(int index){
        if(index<0 || index>=count)
            return -1;
            return data[index];
    }

    //插入元素：头部插入，尾部插入
    public boolean insert(int index,int value){
        //数组中无元素
        if(index == count && count ==0){
            data[index] =value;
            ++count;
            return true;
        }

        //数组已满
        if(count == n){
            System.out.println("没有可插入的位置");
            return false;
        }
        //如果count还没满，那么就可以插入数据到数组中

        //位置不合法时
        if(index < 0 || index > count){
            System.out.println("位置不合法");
            return false;
        }

        //位置合法
        for(int i=count;i>index;--i){
            data[i] = data[i-1];
        }
        data[index] = value;
        ++count;
        return true;
    }

    //根据索引删除数组中的元素
    public boolean delete(int index){
        if(index<0 || index >= count) return false;
        //从删除位置开始，将后面的元素向前移动一位
        for(int i=index+1;i<count;++i){
            data[i-1] = data[i];
        }
        //删除数组末尾元素，这段代码不需要也可以
        /*
        int[] arr = new int[count-1];
        for(int i=0;i<count-1;i++){
        arr[i] = data[i];
        }
        this.data=arr;
         */
        --count;
        return true;
    }
    public void printAll(){
        for(int i=0;i<count;++i){
            System.out.println(data[i]+ " ");
        }
        System.out.println();
    }
    public static void main(String[] args){
        Array array=new Array(5);
        array.printAll();
        array.insert(0,3);
        array.insert(0,4);
        array.insert(0,5);
        array.insert(0,9);
        array.insert(0,10);
        array.printAll();
        System.out.println("-----------");

        System.out.println(array.find(3));
    }
}
























