#include <stdio.h>
#include <ctype.h>
#include <stdlib.h>
#define MAXLINE 100

int contained(unsigned char* from,unsigned char* with,int len){
   // printf("%c,len=%d,symb=%c\n",from[0],len,*with);
    int answ=0;
    for (len;len>=0;len--){
        if (from[len]==*with){
             answ=1;
             break;
        }
        else {
            answ=0;
            continue;
        }
    }
    return answ;
}
//compaire FIRST WITH THE SECOND
void compaire(unsigned char* first,unsigned char* second,int len_first,int len_second,unsigned char* result){
    printf("pointer in funct=%p\n",second);
    printf("first[last]=%c,second[last]=%c\n",first[len_first-1],second[len_second-1]);
    int lenght= len_first-1;
    int i=0;
    len_first=len_first-1;
    len_second=len_second-1;//всякая фигня, как сократить?
     printf("%d",(contained(first[len_first],second[len_second],lenght)));// краш
    printf("first[last]=%c,second[last]=%c\n",first[len_first],second[len_second]);

    for(len_first;len_first>=0;len_first--){
        // в этом теле имеем фиксированну индекс из первого массива
            if ((contained(first[len_first],second[len_second],lenght))==1){
                result[i]=first[len_first];
                        i++;
            }
            else continue;
            }
    }

void main(){
    unsigned char a[MAXLINE];
    unsigned char b[MAXLINE];
    unsigned char s[MAXLINE];
    int i,k=0;
    //const char n[] = "lalalalaal";
    printf("Enter first string__%c\n");
    unsigned char c=0;
    for(i=0;(i<MAXLINE)&&((c=(getchar())) !='\n')&&(c!=EOF);i++){
          a[i]=c;
    }
    int answ;
     //printf("i=%d\n",i);
    //printf("a[i]=%c_\n",(a[i-1]));
    int j=i-1;

     printf("Enter second string__%c\n");
     for(k=0;(k<MAXLINE)&&((c=(getchar())) !='\n')&&(c!=EOF);k++){
           b[k]=c;
     }
    // printf("..%c\n",b[0]);



   // printf("Enter seaching symbol\n");
    //unsigned char symb;

    //scanf("%c",&symb);
   // getchar();

  printf("pointer in main=%p\n",a);
  //  printf("answer=%d\n", (contained(a,&symb,j))    );
    compaire(a,b,i,k,s);
    printf("%-__d\n", s[0] );
}
