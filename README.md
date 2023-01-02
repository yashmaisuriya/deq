#include <stdio.h>
#include<stdlib.h>
# define SIZE 5
void insert();
void delete();
void diplay();
int inp_arr[SIZE];
int Rear = - 1;
int Front = - 1;

int main()
{
    int ch;
    while (1)
    {
        printf("1.insert Operation\n");
        printf("2.delete Operation\n");
        printf("3.Display the Queue\n");
        printf("4.Exit\n");
        printf("Enter your choice of operations : ");
        scanf("%d", &ch);
        switch (ch)
        {
            case 1:
		    insert();
		    break;
            case 2:
		    delete();
		    break;
            case 3:
		    diplay();
		    break;
            case 4:
		    exit(0);
		    default:
            printf("Wrong choice \n");
        } 
    } 
} 
 
void insert()
{
    int item;
    if (Rear == SIZE - 1)
    {
       printf("Queue is Overflow \n");
    }
    else
    {
        if (Front == - 1)
        {      
        	Front = 0;
	        printf("Element to be inserted in the Queue\n : ");
        	scanf("%d", &item);
	        Rear = Rear + 1;
	        inp_arr[Rear] = item;
        }
    }
} 
 
void delete()
{
    if (Front == - 1 || Front > Rear)
    {
        printf("Underflow \n");
        return ;
    }
    else
    {
        printf("Element deleted from the Queue: %d\n", inp_arr[Front]);
        Front = Front + 1;
    }
} 
 
void diplay()
{
    
    if (Front == - 1)
    {
        printf("Empty Queue \n");
    }
    else
    {
        printf("Queue: \n");
        for (int i =0 ; i <= Rear; i++)
        {
		printf("%d ", inp_arr[i]);
		printf("\n");
	}
        
    }
}
