# C Function Pointer

As we know that we can create a pointer of any data type such as int, char, float, we can also create a pointer pointing to a function. The code of a function always resides in memory, which means that the function has some address. We can get the address of memory by using the function pointer.

Let's see a simple example.

#include <stdio.h>  
int main()  
{  
    printf("Address of main() function is %p",main);  
    return 0;  
}  

Output

https://static.javatpoint.com/cpages/images/c-function-pointer.png

# Declaration of a function pointer

Syntax of function pointer

return type (*ptr_name)(type1, type2…); 

For example:

In the above declaration, *ip is a pointer that points to a function which returns an int value and accepts an integer value as an argument.

int (*ip) (int);  

In the above declaration, *fp is a pointer that points to a function that returns a float value and accepts a float value as an argument.

We can observe that the declaration of a function is similar to the declaration of a function pointer except that the pointer is preceded by a '*'. So, in the above declaration, fp is declared as a function rather than a pointer.

Till now, we have learnt how to declare the function pointer. Our next step is to assign the address of a function to the function pointer.


float (*fp) (int , int);    // Declaration of a function pointer.  
float func( int , int );    // Declaration of  function.  
fp = func;                     // Assigning address of func to the fp pointer.  


In the above declaration, 'fp' pointer contains the address of the 'func' function.

# Calling a function through a function pointer

We already know how to call a function in the usual way. Now, we will see how to call a function using a function pointer.

Suppose we declare a function as given below:

float func(int , int);      // Declaration of a function.  
Calling an above function using a usual way is given below:

result = func(a , b);     // Calling a function using usual ways.  
Calling a function using a function pointer is given below:


result = (*fp)( a , b);    // Calling a function using function pointer.  
Or

result = fp(a , b);         // Calling a function using function pointer, and indirection             operator can be removed.  

The effect of calling a function by its name or function pointer is the same. If we are using the function pointer, we can omit the indirection operator as we did in the second case. Still, we use the indirection operator as it makes it clear to the user that we are using a function pointer.

Let's understand the function pointer through an example.


#include <stdio.h>  
int add(int,int);  
int main()  
{  
   int a,b;  
   int (*ip)(int,int);  
   int result;  
   printf("Enter the values of a and b : ");  
   scanf("%d %d",&a,&b);  
   ip=add;  
   result=(*ip)(a,b);  
   printf("Value after addition is : %d",result);  
    return 0;  
}  
int add(int a,int b)  
{  
    int c=a+b;  
    return c;  
}  


Output

https://static.javatpoint.com/cpages/images/c-function-pointer3.png


# Array of Function Pointers

Function pointers are used in those applications where we do not know in advance which function will be called. In an array of function pointers, array takes the addresses of different functions, and the appropriate function will be called based on the index number.


Let's understand through an example.

#include <stdio.h>  
float add(float,int);  
float sub(float,int);  
float mul(float,int);  
float div(float,int);  
int main()  
{  
    float x;              // variable declaration.  
    int y;  
    float (*fp[4]) (float,int);        // function pointer declaration.  
    fp[0]=add;              // assigning addresses to the elements of an array of a function   pointer.  
    fp[1]=sub;  
    fp[2]=mul;  
    fp[3]=div;  
    printf("Enter the values of x and y :");  
    scanf("%f %d",&x,&y);  
  float r=(*fp[0]) (x,y);        // Calling add() function.  
    printf("\nSum of two values is : %f",r);  
     r=(*fp[1]) (x,y);             // Calling sub() function.  
    printf("\nDifference of two values is : %f",r);  
      r=(*fp[2]) (x,y);            // Calliung sub() function.  
    printf("\nMultiplication of two values is : %f",r);  
     r=(*fp[3]) (x,y);           // Calling div() function.  
    printf("\nDivision of two values is : %f",r);  
    return 0;  
}  
  
float add(float x,int y)  
{  
    float a=x+y;  
    return a;  
}  
float sub(float x,int y)  
{  
    float a=x-y;  
    return a;  
}  
float mul(float x,int y)  
{  
    float a=x*y;  
    return a;  
}  
float div(float x,int y)  
{  
    float a=x/y;  
    return a;  
}  

In the above code, we have created an array of function pointers that contain the addresses of four functions. After storing the addresses of functions in an array of function pointers, we call the functions using the function pointer.


Output

https://static.javatpoint.com/cpages/images/c-function-pointer4.png

