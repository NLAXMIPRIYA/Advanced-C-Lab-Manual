EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Functiona
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
#include <stdio.h>

#define SIZE 5

int stack[SIZE];
int top = -1;

void display()
{
    int i;

    if (top == -1)
    {
        printf("Stack is empty\n");
        return;
    }

    printf("Stack elements are:\n");

    for (i = top; i >= 0; i--)
    {
        printf("%d\n", stack[i]);
    }
}

int main()
{
    stack[++top] = 10;
    stack[++top] = 20;
    stack[++top] = 30;
    stack[++top] = 40;

    display();

    return 0;
}



```

Output:

<img width="677" height="167" alt="image" src="https://github.com/user-attachments/assets/5c7fd440-a0d0-4e6f-9bf9-227c5ae4405b" />




Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:

```
#include <stdio.h>

#define SIZE 5

float stack[SIZE];
int top = -1;

void push(float value)
{
    if (top == SIZE - 1)
    {
        printf("Stack Overflow\n");
    }
    else
    {
        top++;
        stack[top] = value;
        printf("%.2f pushed into stack\n", value);
    }
}

int main()
{
    float value;

    printf("Enter element to push: ");
    scanf("%f", &value);

    push(value);

    return 0;
}





```

Output:

<img width="753" height="171" alt="image" src="https://github.com/user-attachments/assets/f105c1c7-dadc-412e-997d-6f84673f2342" />





Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>

#define SIZE 5

float queue[SIZE];
int front = 0;
int rear = 3;

void display()
{
    int i;

    if (front > rear)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements are:\n");

    for (i = front; i <= rear; i++)
    {
        printf("%.2f ", queue[i]);
    }

    printf("\n");
}

int main()
{
    queue[0] = 10.5;
    queue[1] = 20.5;
    queue[2] = 30.5;
    queue[3] = 40.5;

    display();

    return 0;
}



```

Output:

<img width="750" height="179" alt="image" src="https://github.com/user-attachments/assets/17480b3e-c8a1-4bbe-9d97-b108162c5960" />



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>

#define SIZE 5

float queue[SIZE];
int front = -1;
int rear = -1;

void enqueue(float value)
{
    if (rear == SIZE - 1)
    {
        printf("Queue Overflow\n");
    }
    else
    {
        if (front == -1)
        {
            front = 0;
        }

        rear++;
        queue[rear] = value;

        printf("%.2f inserted into queue\n", value);
    }
}

int main()
{
    float value;

    printf("Enter element to insert: ");
    scanf("%f", &value);

    enqueue(value);

    return 0;
}




```

Output:

<img width="760" height="183" alt="image" src="https://github.com/user-attachments/assets/890dff7f-efc5-4c0c-9674-3eb638581cb7" />


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>

#define SIZE 5

int queue[SIZE];
int front = 0;
int rear = 3;

void dequeue()
{
    if (front == -1)
    {
        printf("Queue is empty\n");
    }
    else
    {
        printf("Deleted element: %d\n", queue[front]);

        front++;

        if (front > rear)
        {
            front = -1;
            rear = -1;
        }
    }
}

int main()
{
    queue[0] = 10;
    queue[1] = 20;
    queue[2] = 30;
    queue[3] = 40;

    printf("Queue before deletion:\n");

    for (int i = front; i <= rear; i++)
    {
        printf("%d ", queue[i]);
    }

    printf("\n");

    dequeue();

    printf("Queue after deletion:\n");

    if (front != -1)
    {
        for (int i = front; i <= rear; i++)
        {
            printf("%d ", queue[i]);
        }
    }

    return 0;
}



```

Output:

<img width="760" height="189" alt="image" src="https://github.com/user-attachments/assets/c5bf11a8-edde-4449-a8c2-7db2bcc6404b" />



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
