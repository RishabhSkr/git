# Online_Code


// Online C compiler to run C program online
#include <stdio.h>
#include <stdlib.h>
struct Stack
    {
    	int size;
        int top;
        int *arr;
    };


void create(struct Stack *st)
{
    printf("Enter the Size: ");
    scanf("%d",&st->size);
    st->top=-1;
    st->arr=(int*)malloc(st->size*sizeof(int));
}

void push(struct Stack *st, int value){
    if(st->top==st->size-1)
    {
        printf("Stack is overflow");
    }
    else
    st->top++;
    st->arr[st->top]=value;
}
void Display(struct Stack st){
   int i;
   for( i= st.top;i>=0;i--)
   {
       printf("%d",st.arr[i]);
      printf("  ");
   }
}

int pop(struct Stack *st,int index)
{
    int val=-1;
     if(st->top==-1)
     {
        printf("Stack is Undeflow");
     }
     else
     {
      val=st->arr[st->top--];
     }
     return val;
}

int main() {
	struct Stack st;
	create(&st);
	push(&st,20);
	push(&st,25);
	push(&st,30);
	push(&st,40);

	int poppedElement=pop(&st,0);
	printf("\n thepoppedElementis: %d \n",poppedElement);
	Display(st);
	return 0;
}
