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

