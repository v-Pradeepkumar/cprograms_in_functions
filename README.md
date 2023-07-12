# cprograms_in_functions



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

//4 4





