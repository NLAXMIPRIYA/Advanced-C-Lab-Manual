

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void display()
{
    struct Node *p = head;

    if (p == NULL)
    {
        printf("Stack is empty\n");
        return;
    }

    printf("Stack elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *second, *third;

    head = malloc(sizeof(struct Node));
    second = malloc(sizeof(struct Node));
    third = malloc(sizeof(struct Node));

    head->data = 30;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 10;
    third->next = NULL;

    display();

    free(head);
    free(second);
    free(third);

    return 0;
}




```

Output:

<img width="758" height="185" alt="image" src="https://github.com/user-attachments/assets/3cb8e4a6-09b5-4dad-91eb-0944187df64f" />



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *head = NULL;

void pop()
{
    struct Node *temp;

    if (head == NULL)
    {
        printf("Stack is empty\n");
        return;
    }

    temp = head;

    printf("Popped element: %d\n", head->data);

    head = head->next;

    free(temp);
}

void display()
{
    struct Node *p = head;

    printf("Stack after pop:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *second, *third;

    head = malloc(sizeof(struct Node));
    second = malloc(sizeof(struct Node));
    third = malloc(sizeof(struct Node));

    head->data = 30;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 10;
    third->next = NULL;

    printf("Stack before pop:\n");
    display();

    pop();

    display();

    while (head != NULL)
    {
        struct Node *temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}




```

Output:

<img width="754" height="187" alt="image" src="https://github.com/user-attachments/assets/ca26671e-c716-4f9c-9773-e47fa7be2b02" />




Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void display()
{
    struct Node *p = front;

    if (front == NULL)
    {
        printf("Queue is empty\n");
        return;
    }

    printf("Queue elements are:\n");

    while (p != NULL)
    {
        printf("%d\n", p->data);
        p = p->next;
    }
}

int main()
{
    struct Node *second, *third;

    front = malloc(sizeof(struct Node));
    second = malloc(sizeof(struct Node));
    third = malloc(sizeof(struct Node));

    front->data = 10;
    front->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    rear = third;

    display();

    free(front);
    free(second);
    free(third);

    return 0;
}


```

Output:

<img width="757" height="180" alt="image" src="https://github.com/user-attachments/assets/d491e93c-29fe-45c9-9c64-7f1d9eb93456" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

void enqueue(int value)
{
    struct Node *p;

    p = malloc(sizeof(struct Node));

    p->data = value;
    p->next = NULL;

    if (front == NULL)
    {
        front = p;
        rear = p;
    }
    else
    {
        rear->next = p;
        rear = p;
    }

    printf("%d inserted into queue\n", value);
}

void display()
{
    struct Node *temp = front;

    printf("Queue elements are:\n");

    while (temp != NULL)
    {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main()
{
    int value;

    enqueue(10);
    enqueue(20);
    enqueue(30);

    printf("Queue before insertion:\n");
    display();

    printf("Enter element to insert: ");
    scanf("%d", &value);

    enqueue(value);

    printf("Queue after insertion:\n");
    display();

    while (front != NULL)
    {
        struct Node *temp = front;
        front = front->next;
        free(temp);
    }

    return 0;
}


```

Output:

<img width="755" height="181" alt="image" src="https://github.com/user-attachments/assets/fbb9ed98-ad3f-4364-ab56-90409d994471" />


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

struct Node *front = NULL;
struct Node *rear = NULL;

int peek()
{
    if (front == NULL)
    {
        printf("Queue is empty\n");
        return -1;
    }

    return front->data;
}

int main()
{
    struct Node *second, *third;
    int value;

    front = malloc(sizeof(struct Node));
    second = malloc(sizeof(struct Node));
    third = malloc(sizeof(struct Node));

    front->data = 10;
    front->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    rear = third;

    value = peek();

    if (front != NULL)
    {
        printf("Peek element of queue = %d\n", value);
    }

    free(front);
    free(second);
    free(third);

    return 0;
}



```

Output:

<img width="756" height="185" alt="image" src="https://github.com/user-attachments/assets/17c14ee2-5728-4245-a96c-84ffba1c6df7" />




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


