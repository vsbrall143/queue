# queue
queue operations



#include <stdio.h>
#include <stdlib.h>
#define N 5
int queue[N];
int front = -1;
int rear = -1;
int x;

void enqueue(int x)
{

    if (rear == N - 1)
    {
        printf("Queue Overflow Condition");
    }
    else if (front == -1 && rear == -1)
    {
        front = rear = 0;
        queue[rear] = x;
    }
    else
    {
        rear++;
        queue[rear] = x;
    }
}
void dequeue()
{
    if (front == -1 && rear == -1)
    {
        printf("Queue Underflow Condition");
    }
    else if (front == rear)
    {
        front = rear = -1;
    }
    else
    {
        printf("the dequeued element is %d\n", queue[front]);
        front++;
    }
}
void display()
{
    int i;
    if (front == -1 && rear == -1)
    {
        printf("Queue is Empty");
    }
    else
    {
        printf("\n \n ***The Queue elements are*** \n");
        for (i = front; i < rear + 1; i++)
        {
            printf("%d ", queue[i]);
            printf("\n \n");
        }
    }
}

int main()
{
    int input;
    while(input!=4)
    {
        printf("<<<<<Main Menu>>>>>\n");
        printf("Enter the following choice\n");
        printf("1:Insert\t2:Delete\t3:Display\t4:Exit\n");
        scanf("%d", &input);
        switch (input)
        {
        case 1:
            printf("Enter the element you want to insert\n");
            scanf("%d", &x);
            enqueue(x);
            break;
        case 2:
            dequeue();
            break;
        case 3:
            display();
            break;
        case 4:
            exit(0);
            break;
        default:
            printf("Invalid Input");
        }
    }
}
