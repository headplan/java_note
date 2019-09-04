# 认识数组类型

#### 数组是一种特殊的类

* 数组的类名就是类型带上中括号
* 同一类型的数组 , 每个数组对象的大小可以不一样 . 也就是**每个数组对象占用的内存可以不一样** , 这点和类的对象不同 . 
* 可以用引用指向类型相同大小不同的数组 , 因为它们属于同一种类型

#### 引用数组

可以把类名当成自定义类型 , 定义引用的数组 , 甚至多维数组

```java
package Class;

public class MerchandiseArray {
    public MerchandiseArray() {
    }

    public static void main(String[] args) {
        // >> TODO "数组变量"其背后其实就是引用.数组类型就是一种特殊的类.
        // >> TODO 数组的大小不决定数组的类型.数组的类型是由元素类型决定的.
        int[] intArr;
        intArr = new int[1];
        intArr = new int[2];

        // 这个数组的元素就是二维的double数组,即double[][]
        double[][][] double3DArray;

        int[] a1 = new int[9];
        int[] a2 = new int[0];
        a2 = a1;
        System.out.println("a2.length=" + a2.length);
        double[] a3 = new double[5];
        // a3是double[]类型的引用,不可以用int[]类型的引用赋值
        // a3 ≠ a1;
        double[][][] double3DArray2 = new double[2][3][4];
        double3DArray2[1][2] = a3;
        System.out.println(double3DArray2[1][2]);
    }
}

```



