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
