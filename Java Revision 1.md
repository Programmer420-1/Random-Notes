## Java Revision Part 1

### Introduction
Its been a while since I coded in Java. I only learned and use this programming language when I was in my Pre University last year. I basically have forgotten everything and I decided to relearn this programming language as I will be using this programming language throughout my university life :')
#
### Converting an Integer to its respective string
Coverting an integer to string is very easy in straightforward in Python. I can just do this:

```
    anIntegerString = str(10)
```
But that's not the case in Java. Java syntax is much longer to achieve the same goal. It goes like this:
```
    String anIntegerString = Integer.toString(10)
```
What happen above is I just called the toString method of the Integer class and plugged in the integer as argument into the method. The method will then return me the string version of the Integer. Simple to understand, but tedious syntax :)

### Converting string to Integer or Double
We can just apply the concept of converting Int to String. It is the same concept but the other way around. I will still need to use the method from Integer class, but a different method this time, which is parseInt method. For double datatype we will use parseDouble method from Double class.
```
    int anIntegerFromString = Integer.parseInt("10");
    double aDoubleFromString = Double.parseDouble("3.14");
```
#
### LocalDate Class
__NEVER__ learnt this before. This is the first time I encounter this class. I may be wrong for my understandings on this part of lesson. So here's what I got.

In order to use this class, we have to import the class into our program first. 
```
    import java.time.LocalDate;
```
Then, we will need to instantiate a LocalDate object in a variable. Like so
```
    LocalDate dt;
```
Lets say, I want to know about the day of a week in a particular month of a particular year. I can just do this:
```
    LocalDate gt = LocalDate.of(y,m,d);
    String dayName = dt.getDayOfWeek().name();
```
First line of code will return an instance of LocalDate class from the input of year,month and day. Note that all year, month and day are passed into the method as integer.
<br>
Second line of code will store the name of the day. Things to keep in mind is the .getDayOfWeek() method will return a enum instead of a string. Thus we need to use .name() method from enum class to convert the value into a string and to be stored.
<br>
To do all of this is a line, I can just do this
```
    System.out.println(LocalDate.of(y,m,d).getDayOfWeek());
```
.name() method can be omitted as I am not storing the result.
#


