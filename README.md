# php_practice
QUESTION 1:
%{
#include <stdio.h>
#include <math.h>
int count=0,countx=0 , countz=0; 
%}
%%
[a] {count++;}
[b] {countx++; }
[c] {countz++ ; }
%%
int main()
{
yylex();
if(count%2==0 && countx%2==1 && countz%2==0)
printf("String accepted");
else
printf("String not accepted");
return 0;
}
int yywrap()
{
return 1;
}





Question 2:

%{
#include<stdio.h>
#include<stdlib.h>
int flag,c,j;
%}
%%
[0-9]+ {c=atoi(yytext);
if(c==2)
{
printf("\n Prime number");
}
else if(c==0 || c==1)
{
printf("\n Not a Prime number");
}
else
{
for(j=2;j<c;j++)
{
if(c%j==0)
flag=1;
}
if(flag==1)
printf("\n Not a prime number");
else if(flag==0)
printf("\n Prime number");
}
}
%%int main()
{
printf("Input:\n");
yylex();
return 0;
}
int yywrap()
{
return 1;
}
