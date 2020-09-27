# Railway-Reservation-System
This is my first C Project at year 2014-15
as this project is developed in 2015 some files i have not complete code so i can attatch here code as a text
CODING
#include <stdio.h>
#include<string.h>
#include <stdlib.h>
#include<conio.h>
#define M printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
#define P printf("\n*");
//****************************************************************************************************
                          //           FUNCTION DECLARATION     //
//*****************************************************************************************************
void add();
void view_t();
void delete_info();
void add_disp();
void psdt();
void pview();
void psrch();
void pmodify();
void pdlt();

//*********************************************************************************************************



















                                             //TRAIN DETAIL
//**********************************************************************************************************
struct train_det
{
       int atime;
       int dtime;
       int tno;
       char nm[20];
};
//*********************************************************************************************************
                                      // USER DETAIL //
//*********************************************************************************************************                                      
struct user_detail
{
     int train_no;
     int age;
     char unm[20];
     char ufm[5];
     char uto[5];
     char mo_no[10];
     char date[10];       
}p;




















//*********************************************************************************************************
                          // DELETE TRAIN DETAIL //
//*********************************************************************************************************                           
     struct train_delete
     {
       int no;
       int atime;
       int dtime;
       int tno;
       char nm[20];
       }i1;
//*********************************************************************************************************       
                                        // TRAIN INSERT //
//*********************************************************************************************************                                        
struct train_insert
{
       int atime;
       int dtime;
       int tno;
       char nm[20];
};
//*********************************************************************************************************
                              


















           // ADMIN UPDATE //
//*********************************************************************************************************                
void update()
{
       FILE *f;
       char pwd[3],cty[5],no[10];
      system("cls");
      f=fopen("d:\\admin.txt","w");
    
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
    printf("\n\n\n\t\tWELCOME TO PROJECT OF RAILWAY RESERVATION\n\n\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$"); 
      printf("\n\n\n\t\t\t\t NEW PASSWORD");
      scanf("%s",pwd);
      printf("\n\n\n\t\t\t\t ENTER NEW CITY NAME");
      scanf("%s",cty);
      printf("\n\n\n\t\t\t\t ENTER NEW CONTACT NUMBER");
      scanf("%s",no);
      fprintf(f,"%s %s %s",pwd,cty,no);
     fclose(f);
     getch(); 
}
            


















//********************************************************************************************************* 
    //ADMIN INFORMATION //
//*********************************************************************************************************
void adm_info()
{   
    FILE *f;
    char pwd[3],cty[5],no[10];
    system("cls");
       
     printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
    printf("\n\n\n\t\tWELCOME TO PROJECT OF RAILWAY RESERVATION\n\n\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$"); 
    f=fopen("d:\\admin.txt","r");
    fscanf(f,"%s %s %s",&pwd,&cty,&no);
    printf(" \n\n\n\t\t\t\t ADMIN NAME :- DIVYA PATEL");
    printf("\n\n\n\t\t\t\t ADMIN PASSWORD :-%s",pwd);
    printf("\n\n\n\t\t\t\t CITY :- %s",cty);
    printf("\n\n\n\t\t\t\t CONTACT INFO. :- %s",no);
    getch();
}
//*********************************************************************************************************
                     // ADMIN MAIN MENUS//
















//*********************************************************************************************************
void choice()
{
     system("cls");
       printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
    printf("\n\n\n\t\tWELCOME TO PROJECT OF RAILWAY RESERVATION\n\n\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$"); 
     int no;
     printf("\n\n\n\t\t\t\t 1.VIEW INFO.");
     printf("\n\n\n\t\t\t\t 2.UPDATE INFO");
     printf("\n\n\n\t\t\t\t SELECT YOUR CHOICE");
     scanf("%d",&no);
     switch(no)
     {
               case 1:
               adm_info();
               break;
              
              case 2:
              update();
              break;            
      }
      


















 }
//*********************************************************************************************************
                                             // UPDATE ADMIN //
//*********************************************************************************************************
  void update_adm()
{
              int no,atime,dtime;
              FILE *fp,*f;
              char nm[5];
              system("cls");
               printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$");
    printf("\n\n\n\t\tWELCOME TO PROJECT OF RAILWAY RESERVATION\n\n\n");
    printf("$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$"); 
       

           f=fopen("d:/temp.txt","w");
           fp=fopen("d:/train_dat1.txt","r");
           printf("Enter Updated Train no");
           scanf("%d",&no);
           while(fscanf(fp,"\n%d\t%s\t%d\t%d",&i1.tno,i1.nm,&i1.atime,&i1.dtime)!=EOF)
     {
            if(no==i1.tno)

















      {
                      printf("TRAIN NO.:-");
                      scanf("%d",&no);
                      printf("TRAIN NAME:-");
                      scanf("%s",&nm);
                      printf("TIME OF ARRIVAL:-");
                      scanf("%d",&atime);
                      printf("TIME OF DEPARTUAL:-");
                      scanf("%d",&dtime);
                      fprintf(f,"\n%d\t%s\t%d\t%d",no,nm,atime,dtime);
      }
      else
      {
           fprintf(f,"\n%d\t%s\t%d\t%d",i1.tno,i1.nm,i1.atime,i1.dtime);
      }
     }
       fclose(fp); 
       fclose(f);
       f=fopen("d:/temp.txt","r");
       fp=fopen("d:/train_dat1.txt","w");
       while(fscanf(f,"\n%d\t%s\t%d\t%d",&i1.tno,i1.nm,&i1.atime,&i1.dtime)!=EOF)
     {
             fprintf(fp,"\n%d\t%s\t%d\t%d",i1.tno,i1.nm,i1.atime,i1.dtime);        
     }     
     





