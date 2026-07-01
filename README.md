//Queue
#include<stdio.h>
#define MAX 5

int queue [MAX];
int front=-1, rear=-1;

void enqueue(int x) {
	if(rear == MAX-1) {
		printf("The Q is full!!\n");
	}
	else{
		if(front==-1) front=0;
		rear++;
	    queue[rear] = x;
	    printf("%d has been Queued! \n", x);
	}
}

int dequeue(){
	if(rear==-1 && front==-1){
		printf("The Q is Empty!! \n");
		front=rear=-1;
	}
	else
	{
		int x = queue[front];
		front++;
		if(front>rear){
		front=rear=-1;
		};
		printf("%d has been dequeued! \n",x);
		return x;
	}
}

int main(int argc, char** argv)
{
	enqueue(10);
	enqueue(20);
	enqueue(30);
	enqueue(40);
	enqueue(50);
	enqueue(60);//full
	dequeue();
	dequeue();
	dequeue();
	dequeue();
	dequeue();
	dequeue();//empty
}
