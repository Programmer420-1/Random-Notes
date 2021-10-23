# Generic Methods in Java
## Introduction
One day I was think about how can I not implement the same methods which have the same functionality for couple of time just to ensure the method is still functionable despite the datatypes keyed in by the user is different. For example, to implement an addition method, we need to take all numbers datatype (integer, double, float) into considerations. Here's how I do it with method overriding:
```
    static int addition(int a,int b){
        return a+b;
    }
    
    static double addition(double a,double b){
        return a+b;
    }
    
    static float addition(float a,float b){
        return a+b;
    }
```
Look, three of the methods serve the same functionality which is return the value of `a` + `b`, but each takes in and returns value of different datatype. We have to write the same method for 3 times just to support `double` and `float` addition. Just imagine that if we need to implement a sorting algorithm, we will have to write the same piece of codes for 3 times and then we change the arguments and return datatype into other numbers datatype. This does not promote code reusability and readability. Besides that, programmer may also prompt to make mistakes while doing that.
<br><br>
## Generic Methods
Generic methods are methods that introduce their own type parameter. The type parameter is then replaced with actual concrete type during generic instantiation.With generic methods, we can overcome this issues with ease. We are able to implement just a method and the method is able to process the arguments and return value of different datatype.
```
    public static <T> boolean isEquivalent(T a, T b){
        if(a.equals(b)){
            return true;
        }
        return false;
    }
    
    public static void main(String args[]) {
      int integer = 12;
      double deci = 13.0;
      float shortDeci = 14.0f;
      String word = "RickRolled";

      System.out.println(isEquivalent(integer,integer));
      System.out.println(isEquivalent(deci,deci));
      System.out.println(isEquivalent(shortDeci,shortDeci));
      System.out.println(isEquivalent(word,word));
    }
```
Console:
```
    true
    true
    true
    true
```
As we can see, we just write 1 method for arguments of different datatype and the code doesn't break while plugging 4 of those test values into the method.

## Generic Class
Besides generic method, we also have a generic class. ArrayList class is a good generic class example. By inserting the class of datatype we want to use into the `<>`, we can create a dynamic array of desired datatype with a lot of functionality. Just like this:
```
    ArrayList<String> arr = new ArrayList<String>();
```
The idea of how to create a generic class is almost the same as creating a generic method. The following code is how to achieve that.
```
    class printElemArray<T>{
        private T[] arr;
        
        printElemArray(T[] arr){
            this.arr = arr;
        }

        public void printAll(){
            for (int i = 0; i < arr.length ; i++){
                System.out.print(arr[i]+" ");
            }
            System.out.println();
        }
    }

    class Main {
        public static void main(String[] args){
            Integer[] array1 = {1,2,3,4,5,6,7};
            Character[] array2 = {'A','B','C','D','E','F','G'};
            Double[] array3 = {1.1,2.2,3.3,4.4,5.5,6.6,7.7};
            printElemArray<Integer> arr1 = new printElemArray<>(array1);
            printElemArray<Character> arr2 = new printElemArray<>(array2);
            printElemArray<Double> arr3 = new printElemArray<>(array3);
            arr1.printAll();
            arr2.printAll();
            arr3.printAll();
        }
    }
```
Thats it, a generic class which you pass in all datatypes as argument and it doesn't need a lot of implementation!
#
## Generic Bounded Type Parameters
