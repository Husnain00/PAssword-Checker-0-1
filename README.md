/*Name:Hasnain Afridi
Teacher:Sir Imran Ali
Class:BSCS Sec B
Version:0.1
Program Writen in Code::Bloxs 17.12
Why We Use:
In this Program we check the Length And Power Of a Password
If Password has Capital Letters, Small Letters and Special Symbols
so it will show us 1 other wise it will show us 0
*/

#include<stdio.h>
#include<ctype.h>

int length(char array[]);
int strongpwd(char array[]);

int main()

{
char password[]="123456";
char password2[]="qwerty";
char password3[]="qwerty123";
char password4[]="14July_2020!";


printf("\n1. Length of password: \t %s is %d", password, length(password));
printf("\n2. Length of password2:\t %s is %d", password2, length(password2));
printf("\n3. Length of password3:\t %s is %d", password3, length(password3));
printf("\n4. Length of password4:\t %s is %d", password4, length(password4));
printf("\n");
printf("====================Power OF PASSWORD====================");
printf("\n");

printf("\n1. Strength of password: \t %s is %d", password, strongpwd(password));
printf("\n2. Strength of password2:\t %s is %d", password2, strongpwd(password2));
printf("\n3. Strength of password3:\t %s is %d", password3, strongpwd(password3));
printf("\n3. Strength of password4:\t %s is %d", password4, strongpwd(password4));


printf("\n");
 return 0;
 }

 int length(char array[])
 {
 int length=0;
 int count=0;
  while(array[count] != '\0')
  {
   length++;
    count++;
     }
      return length;

  }
//******************
      int strongpwd(char array[])
  {
   int strong=0;

   int InvalidPassword=0;
   int WeakPassword=0;
   int MediumPassword=0;
   int StrongPassword=0;

   int size = length(array);
   for(int i = 0;i<length(array); i++)
   {
   	if(array[i] >= 'A' && array[i]<='Z')

   InvalidPassword=1;

   	else
        if(array[i]>='a' && array[i]<='z')

    WeakPassword=1;
    else if(array[i]>='0' && array[i]<='9')
    MediumPassword=1;
	else
        if(array[i]=='@'||array[i]=='!'||array[i]=='_')
   	StrongPassword=1;
   	}
   	if(InvalidPassword && WeakPassword && MediumPassword && StrongPassword && (size >= 8))
   strong=1;
   	return strong;
	}



