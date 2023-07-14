# cprograms_in_functions.



// function to find the area of reactangle
#include <stdio.h>
int areaOfRect(int length, int breadth)
{
    int area;
    area = length * breadth;
    return area;
}
int main()
{
 int l=50, b=50;
 int area = areaOfRect(l,b);
    printf("%d\n",area);

    return 0;
}



//function for return a character
#include <stdio.h>

char fun();

int main()
{
 char c = fun();
 printf("character is; %c",c);
}

   char fun()
   {

    return 'a';
}

//function for adding two numbers
#include <stdio.h>

int add(int,int);

int main()
{
 int m =20, n = 30, sum;
 sum = add(m, n);
 printf("sum is; %d",sum);
 return 0;
}

   int add(int a, int b)
   {

    return (a + b);
}




//function for call by reference
#include <stdio.h>

int fun(int*ptr1,int*ptr2)
{
    *ptr1 = 20 ; 
    *ptr2 = 10 ;
}

int main()
{
    
 int x = 10, y = 20 ;
fun(&x, &y) ;
printf("x = %d, y= %d",x,y);

}




//function for call by value
#include <stdio.h>

int fun(int x,int y)
{
    x = 20 ; 
    y = 10 ;
}

int main()
{
    
 int x = 10, y = 20 ;
fun(x, y) ;
printf("x = %d, y= %d",x,y);

}




//function for iteration(shift towards right) until 0 code
#include <stdio.h>

int main()
{
    int func(int num)
    {
         int count = 0 ;
          
         while(num)
        { 
             count++;
              num >>=1 ; 
        }
        return (count);
    }
}


//function for static function in c
#include <stdio.h>

 int fun()
    {
        static int num = 16 ;
        return num--;
    }
       
int main()
{
      
       for(fun(); fun(); fun())
       printf(" %d",fun());
        return 0;
    }
    //o/p14 11 8 5 2






 // static(only the function scope is valid in its own block only ) and dynamic scoping(fun1 is having scope in main function also) here is the example of dynamic scoping 
#include <stdio.h>

int main() 
    {
      int a =10 ; 
         a= fun1(a) ;
        printf("%d",a);
    }
int fun1 (int a)
              {
                int b =5 ;
                b = b+a ;
                return b;
             }






// static(only the function scope is valid in its own block only ) and dynamic scoping(fun1 is having scope in main function also). in those 2 cases we knows well aboit stack memory thi program for static scoping . scoping is only for reuse the same variable with different values in different blocks

#include <stdio.h>
int fun1(int) ;
int fun2(int) ;
int a = 5 ;
int main() 
    {
      int a =10 ; 
         a= fun1(a) ;
        printf("%d",a);
    }
int fun1 (int b)
              {
                b = b+10 ;
                b = fun2(b) ;
                return b;
             }
int fun2 (int b)
                {
                    int c ;
                    c = b + a ; 
                    return c ;
                }





// c programing using static scoping 
#include <stdio.h>
int x = 50 ;
int fun2()
{
    return x ;
}
int fun1()
{
    int x = 10 ;
    int y = fun2 () ;
    return y;
}
int main()
{
  
printf("%d",fun1());
}

//o/p 50






// pseudocode parameters are passed by reference not by value
#include <stdio.h>
int a = 3 ;
void n( x)
{
     x= x * a ;
     print(x);
}
void m(y) 
{
   a = 1 ;
   a = y- a ;
   n(a);
   print(a) ;
}
void main()
{
m(a);
}

//o/p..4 4





// recursion (function call by itself)
#include <stdio.h>
int fun(int n)

{
     if(n==1)
     return 1;
     else
     return 1 + fun(n-1) ;
}

int main()
{
int n = 3 ;
printf("%d",fun(n)) ;
return 0 ;
}

//o/p 3






// recursion (function call by itself)
#include <stdio.h>
int fact(int n)

{
     if(n==1)
     return 1;
     else
     return n * fact(n-1) ;
}

int main()
{
int n ;
printf("enter the number : ") ;
scanf("%d",&n);
printf("factorial of a number %d is %d ",n,fact(n)) ;
}

//5 factorial is 120






// write a program to print from 1 to 10 in such a way tat when number is odd,add1 and when number is even,subtract 1.output: 2 1 4 3 6 5 8 7 10 9 this is for indirect recursion [fun1() directly calling the fun()]
#include <stdio.h>
void odd() ;
void  even() ;
int n = 1 ;
void odd(){
    if(n<=10)
    {
        printf("%d ",n+1) ;
    n++;
    even() ;
    }
    return ;
}
void even()
{
    if(n<=10)
    {
        printf("%d ",n-1) ;
        n++ ;
        odd();
}
return;
}
int main()
{
    odd() ;
}




//tailrecursion
//a recursive function is said to be tail recursive if the recursive call is the last thing done by the function.(function call at the last line of code after no execution happened) o/p 3 2 1
#include <stdio.h>

void fun(int n){
    if(n==0)
    {
    return ;
}
    else
    {
        printf("%d ",n) ;
        
return fun(n-1);
}
}
int main()
{
    fun(3) ;
    return 0;
}





//a recursive function is said to be non tail recursive if the recursive call is not the last thing done by the function.after returning back,there is something left to evaluate o/p=3
#include <stdio.h>

int fun(int n){
    if(n==1)
     {
         return 0 ;
     }
    else
     {
        return 1 + fun(n/2);
      }
    }
  int main()
{
    printf("%d",fun(8)) ;
    return 0;
}




//iterative program to calculate factorial(but recursion is best bcz lessline of code)
#include <stdio.h>

int fact(int n){
    int res = 1 ;
    while(n!=0)
    {
        res = res * n ;
        n-- ;
    }
    return res;
    }
  int main()
{
    printf("%d",fact(6)) ;
    return 0;
}









// BASICS OF ARRAY declare- datatype array name [size] first index of an array=0 end of index should (n-1) using macro in array is best practice example; #define N 10
   //int array [N];   -here is the example with macro(#define)
#include <stdio.h>
#define N 10

int main() {
    int a[N] , i ;
    for(i=0;i<N;i++)
    {
     printf("enter the input for index %d:",i);
     scanf("%d",&a[i]);
    }
    printf("\n array elements are as follows:\n");
        for(i=0;i<N;i++)
         {
             printf(" %d",a[i]);
         }

    return 0;
}
//here arr[10]={1,2,3,[2]=5,[6]=8}={1,2,5,0,0,0,8,0,0,0}








// print reversal order of a array
#include <stdio.h>

int main() {
    int a [9] = {34, 56, 54, 32, 67, 89, 90, 32, 21};
    int i;
    //original order
    for(i=0;i<9;i++)
        {
             printf("%d ", a[i]);
         }
              printf("\n");
         for(i=8;i>=0;i--)
             {
                 printf("%d ", a[i]);
              }

    return 0;
}
//34 56 54 32 67 89 90 32 21 
21 32 90 89 67 32 54 56 34 




// repeated numbers are presented or not code in an array 
#include <stdio.h>

int main() {
    int seen [10] = {0};
    int N ; 
    printf("Enter the Number: ");
    scanf("%d",&N);
    
    int rem;
         while(N>0)
         {
               rem = N%10 ; 
                if(seen [rem] == 1)
                 break;
                 seen[rem] = 1;
                 N = N/10;
        }
         if(N>0)
        printf("yes");
        else
         printf("no");

    return 0;
}








// find how many numbers are presented in an array = total size of array/one element space 
#include <stdio.h>

int main() {
    int seen [] = {100,50,200,100};
    
         printf("%d",sizeof(seen)/sizeof(seen[0]));

    
}







// find the sum of row and column using loops
#include <stdio.h>

int main() {
    int a [2][3] = {
        {1, 3, 0},
         {-1, 5, 9}
    };
    int i,j ;
    int sum = 0 ;
    printf("row total: ");
    
    for(i=0 ; i<2 ;i++ )
    {
        for(j=0 ; j<3 ; j++)
        {
            sum += a[i][j] ;
        }
        printf("%d ",sum) ;
        sum = 0 ;
    }
                     
    
         printf("\n column total: ") ;
         for(j=0 ; j<3 ;j++ )
         {
        for(i=0 ; i<2 ; i++)
        {
            sum += a[i][j] ;
        }
        printf("%d ",sum) ;
        sum = 0 ;
    }
    return 0 ;
}

    


// matrix multiplication resultant of matrix 1st matrix row and second matrix column num = resultant matri's row and column
#include <stdio.h>
#define MAX 50

int main() {
    int a [MAX][MAX] , b[MAX][MAX] , product[MAX][MAX] ;
    int arows , acolumns , brows , bcolumns ;
    int i, j, k ;
    int sum ;
    printf("Enter The rows and columns ofthe matrix a: ") ;
    scanf("%d %d",&arows , &acolumns) ;
    
    
    printf("Enter The elements ofthe matrix a:\n") ;
    for(i = 0 ;i<arows ;i++)
    {
        for(j=0 ;j<acolumns ;j++)
        {
            scanf("%d ",&a[i][j]) ;
        }
    }
    
    
    
    printf("Enter The rows and columns ofthe matrix b: ") ;
    scanf("%d %d ",brows , bcolumns) ;
    if(brows !=acolumns)
    {
        printf("sorry! we cannot multiply the matrices a and b") ;
    }
    else
    {
        printf ("enter the elements of matrix b:\n") ;
        for(i=0 ; i<brows ; i++)
        {
            for(j = 0 ; j < bcolumns ; j++)
            { 
                scanf("%d ",&b[i][j]) ;
            }
        }
            
        }
        printf("\n") ;
         for(i=0 ; i<arows ; i++)
        {
            for(j = 0 ; j < bcolumns ; j++)
            { 
                for(k = 0 ; k < brows ; k++)
                {
                    sum += a[i][k] *b[k][j] ;
                    
                }
                product[i][j] = sum ;
                sum = 0 ;
    }
        }
        printf("resultant matrix\n") ;
        for(i = 0 ; i < arows ; i++)
        {
            for(j = 0 ; j < bcolumns ; j++)
            {
                printf("%d ",product[i][j]) ;
            }
            printf("\n") ;
        }
        return 0 ;
}







