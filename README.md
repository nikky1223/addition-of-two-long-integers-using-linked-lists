//addition-of-two-long-integers-using-linked-lists

//including header files
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

//creating global int,char arrays
char m[30],n[30];
int v[30],count;

//creating structure
struct node
{
    int data;
    struct node* link;
};
struct node *root1=NULL;
struct node *root2=NULL;
struct node *result=NULL;
void insert1()
{   struct node* temp;
    temp=(struct node*)malloc(sizeof(struct node));
    int x=0;
    temp->data=x;
    temp->link=NULL;
    if(root1==NULL)
        root1=temp;
    else
    {   struct node* p;
        p=root1;
        while(p->link!=NULL)
            p=p->link;
        p->link=temp;
    }
}
void insert2()
{   struct node* temp;
    temp=(struct node*)malloc(sizeof(struct node));
    int x=0;
    temp->data=x;
    temp->link=NULL;
    if(root2==NULL)
        root2=temp;
    else
    {   struct node* p;
        p=root2;
        while(p->link!=NULL)
            p=p->link;
        p->link=temp;
    }
}
void insert3()
{   struct node* temp;
    temp=(struct node*)malloc(sizeof(struct node));
    int x=0;
    temp->data=x;
    temp->link=NULL;
    if(result==NULL)
        result=temp;
    else
    {   struct node* p;
        p=result;
        while(p->link!=NULL)
            p=p->link;
        p->link=temp;
    }
}
void display()
{
    printf("display\n");
    struct node*temp;
    if(root1==NULL)
    {
        printf("list is empty");
    }
    else
    {
        temp=root1;
        printf("root1:");
        while(temp!=NULL)
        {
            printf("%d",temp->data);
            temp=temp->link;
        }
        printf("\n");
    }
    if(root2==NULL)
    {
        printf("list is empty");
    }
    else
    {
        temp=root2;
        printf("root2:");
        while(temp!=NULL)
        {
            printf("%d",temp->data);
            temp=temp->link;
        }
        printf("\n");
    }
    if(result==NULL)
    {
        printf("list is empty");
    }
    else
    {
        temp=result;
        printf("result:");
        while(temp!=NULL)
        {
            printf("%d",temp->data);
            temp=temp->link;
        }
        printf("\n");
    }
    
}
void su()
{   struct node*temp;
    temp=root1;
    for(int i=strlen(n)-1;i>=0;i--)
    {   temp->data=n[i]-'0';
        temp=temp->link;
    }
    temp=root2;
    for(int i=strlen(m)-1;i>=0;i--)
    {   temp->data=m[i]-'0';
        temp=temp->link;
    }
}
void a()
{   struct node *temp1,*temp2,*temp3;
    temp1=root1;
    temp2=root2;
    temp3=result;
    while(temp1!=NULL)
    {   int c;
        c=temp2->data+temp1->data+temp3->data;
        temp1=temp1->link;
        temp2=temp2->link;
        if(c>9)
        {   temp3->data=c%10;
            temp3->link->data=c/10;
            temp3=temp3->link;
        }
        else
        {   temp3->data=c;
            temp3=temp3->link;
        }
        
    }
}
void dr()
{   struct node *temp;
    int c=0;
    temp=result;
    while(temp!=NULL)
    {   v[c]=temp->data;
        c=c+1;
        temp=temp->link;
    }
    printf("Sum is: ");
    for(int i=count;i>=0;i--)
        printf("%d",v[i]);
}
void main()
{   int c=0,b,count1=0,count2=0;
    printf("Enter 1^st Number: ");
    scanf("%s",n);
    printf("Enter 2^nd Number: ");
    scanf("%s",m);
    c=strlen(n);
    b=strlen(m);
    count=c;
    if(b>c)
        count=b;
    for(int i=count+1;i>0;i--)
    {   insert1();
        insert2();
        insert3();
    }
    printf("before substuting values");
    display();
    su();
    printf("after substition");
    display();
    a();
    printf("after adding");
    display();
    dr();
}










