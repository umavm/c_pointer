 **A pointer is a variable in C, and pointers value is the address of a memory location.**

 The size of the pointer depends on the architecture. However, in 32-bit architecture the size of a pointer is 2 byte.

 Example:

int n = 10;   
int* p = &n; // Variable p of type pointer is pointing to the address of the variable n of type integer. 

# Declaring a pointer

The pointer in c language can be declared using * (asterisk symbol). It is also known as indirection pointer used to dereference a pointer.

int *a;//pointer to int  
char *c;//pointer to char

## Pointer Example
https://static.javatpoint.com/cpages/images/pointer.png

As you can see in the above figure, pointer variable stores the address of number variable, i.e., fff4. The value of number variable is 50. But the address of pointer variable p is aaa3.

By the help of * (indirection operator), we can print the value of pointer variable p.

Let's see the pointer example as explained for the above figure.

#include<stdio.h>  
int main(){  
int number=50;    
int *p;      
p=&number;//stores the address of number variable    
printf("Address of p variable is %x \n",p); // p contains the address of the number therefore printing p gives the address of number.     
printf("Value of p variable is %d \n",*p); // As we know that * is used to dereference a pointer therefore if we print *p, we will get the value stored at the address contained by p.    
return 0;  
}    

Output

Address of number variable is fff4
Address of p variable is fff4
Value of p variable is 50

# Pointer to array

int arr[10];  
int *p[10]=&arr; // Variable p of type pointer is pointing to the address of an integer array arr. 

# Pointer to a function

void show (int);  
void(*p)(int) = &display; // Pointer p is pointing to the address of a function

# Pointer to structure
struct st {  
    int i;  
    float f;  
}ref;  
struct st *p = &ref;  

https://static.javatpoint.com/cpages/images/cpointer1.png




