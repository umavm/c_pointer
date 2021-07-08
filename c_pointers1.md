# Advantage of pointer

1) Pointer reduces the code and improves the performance, it is used to retrieving strings, trees, etc. and used with arrays, structures, and functions.

2) We can return multiple values from a function using the pointer.

3) It makes you able to access any memory location in the computer's memory.

# Usage of pointer

There are many applications of pointers in c language.

1) Dynamic memory allocation

In c language, we can dynamically allocate memory using malloc() and calloc() functions where the pointer is used.

2) Arrays, Functions, and Structures

Pointers in c language are widely used in arrays, functions, and structures. It reduces the code and improves the performance.

## Address Of (&) Operator

The address of operator '&' returns the address of a variable. But, we need to use %u to display the address of a variable.

#include<stdio.h>  
int main(){  
int number=50;   
printf("value of number is %d, address of number is %u",number,&number);    
return 0;  
}   


Output

value of number is 50, address of number is fff4

# NULL Pointer

A pointer that is not assigned any value but NULL is known as the NULL pointer. If you don't have any address to be specified in the pointer at the time of declaration, you can assign NULL value.

int *p=NULL;

## Pointer Program to swap two numbers without using the 3rd variable.

#include<stdio.h>  
int main(){  
int a=10,b=20,*p1=&a,*p2=&b;  
  
printf("Before swap: *p1=%d *p2=%d",*p1,*p2);  
*p1=*p1+*p2;  
*p2=*p1-*p2;  
*p1=*p1-*p2;  
printf("\nAfter swap: *p1=%d *p2=%d",*p1,*p2);  
  
return 0;  
}  

Output

Before swap: *p1=10 *p2=20
After swap: *p1=20 *p2=10

## Reading complex point

There are several things which must be taken into the consideration while reading the complex pointers in C. Lets see the precedence and associativity of the operators which are used regarding pointersers



Operator	   Precedence	    Associativity

(), []	        1	          Left to right
*, identifier	  2	          Right to left
Data type	      3	                 -



(): This operator is a bracket operator used to declare and define the function.
[]: This operator is an array subscript operator
* : This operator is a pointer operator.
Identifier: It is the name of the pointer. The priority will always be assigned to this.
Data type: Data type is the type of the variable to which the pointer is intended to point. It also includes the modifier like signed int, long, etc).


## How to read the pointer: int (*p)[10].

To read the pointer, we must see that () and [] have the equal precedence. Therefore, their associativity must be considered here. The associativity is left to right, so the priority goes to ().

Inside the bracket (), pointer operator * and pointer name (identifier) p have the same precedence. Therefore, their associativity must be considered here which is right to left, so the priority goes to p, and the second priority goes to *.

Assign the 3rd priority to [] since the data type has the last precedence. Therefore the pointer will look like following.

char -> 4
* -> 2
p -> 1
[10] -> 3


The pointer will be read as p is a pointer to an array of integers of size 10.

Example:

How to read the following pointer?

int (*p)(int (*)[2], int (*)void))  

## Explanation

This pointer will be read as p is a pointer to such function which accepts the first parameter as the pointer to a one-dimensional array of integers of size two and the second parameter as the pointer to a function which parameter is void and return type is the integer.
