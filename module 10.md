EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node
{
    char data;
    struct node *next;
};

void search(struct node *head, char key)
{
    struct node *temp = head;
    int position = 1;

    while (temp != NULL)
    {
        if (temp->data == key)
        {
            printf("Element %c found at position %d\n", key, position);
            return;
        }

        temp = temp->next;
        position++;
    }

    printf("Element %c not found\n", key);
}

int main()
{
    struct node *head, *second, *third;
    char key;

    head = malloc(sizeof(struct node));
    second = malloc(sizeof(struct node));
    third = malloc(sizeof(struct node));

    head->data = 'A';
    head->next = second;

    second->data = 'B';
    second->next = third;

    third->data = 'C';
    third->next = NULL;

    printf("Linked list: A -> B -> C\n");

    printf("Enter element to search: ");
    scanf(" %c", &key);

    search(head, key);

    free(head);
    free(second);
    free(third);

    return 0;
}



```

Output:

<img width="757" height="190" alt="image" src="https://github.com/user-attachments/assets/210e1468-5060-44a6-be63-e5b7e28b5197" />




Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node
{
    char data;
    struct node *next;
};

void insert(struct node **head, char value)
{
    struct node *newNode;
    struct node *temp;

    newNode = malloc(sizeof(struct node));

    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
        return;
    }

    temp = *head;

    while (temp->next != NULL)
    {
        temp = temp->next;
    }

    temp->next = newNode;
}

void display(struct node *head)
{
    struct node *temp = head;

    while (temp != NULL)
    {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct node *head = NULL;
    char value;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    printf("Linked list before insertion:\n");
    display(head);

    printf("Enter element to insert: ");
    scanf(" %c", &value);

    insert(&head, value);

    printf("Linked list after insertion:\n");
    display(head);

    return 0;
}






```

Output:

<img width="755" height="187" alt="image" src="https://github.com/user-attachments/assets/2b5df4cd-37b6-47ce-9f19-413d584646c8" />


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};

void display(struct node *head)
{
    struct node *temp = head;

    while (temp != NULL)
    {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct node *head;
    struct node *second;
    struct node *third;

    head = malloc(sizeof(struct node));
    second = malloc(sizeof(struct node));
    third = malloc(sizeof(struct node));

    head->data = 10;
    head->prev = NULL;
    head->next = second;

    second->data = 20;
    second->prev = head;
    second->next = third;

    third->data = 30;
    third->prev = second;
    third->next = NULL;

    printf("Doubly linked list:\n");

    display(head);

    free(head);
    free(second);
    free(third);

    return 0;
}




```

Output:

<img width="757" height="191" alt="image" src="https://github.com/user-attachments/assets/2aeb25a3-a6b1-4b86-b281-d4fa91917cee" />



Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *prev;
    struct node *next;
};

void insert(struct node **head, int value)
{
    struct node *newNode;
    struct node *temp;

    newNode = malloc(sizeof(struct node));

    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;

    if (*head == NULL)
    {
        *head = newNode;
        return;
    }

    temp = *head;

    while (temp->next != NULL)
    {
        temp = temp->next;
    }

    temp->next = newNode;
    newNode->prev = temp;
}

void display(struct node *head)
{
    struct node *temp = head;

    while (temp != NULL)
    {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct node *head = NULL;
    int value;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);

    printf("Doubly linked list before insertion:\n");
    display(head);

    printf("Enter element to insert: ");
    scanf("%d", &value);

    insert(&head, value);

    printf("Doubly linked list after insertion:\n");
    display(head);

    return 0;
}




```

Output:

<img width="754" height="189" alt="image" src="https://github.com/user-attachments/assets/8baab73a-30bc-4033-a6d8-1f659452f73c" />



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:
```
#include <stdio.h>
#include <stdlib.h>

struct node
{
    int data;
    struct node *next;
};

void deleteElement(struct node **head, int value)
{
    struct node *temp;
    struct node *prev;

    if (*head == NULL)
    {
        printf("Linked list is empty\n");
        return;
    }

    temp = *head;
    prev = NULL;

    while (temp != NULL && temp->data != value)
    {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL)
    {
        printf("Element %d not found\n", value);
        return;
    }

    if (prev == NULL)
    {
        *head = temp->next;
    }
    else
    {
        prev->next = temp->next;
    }

    free(temp);

    printf("Element %d deleted successfully\n", value);
}

void display(struct node *head)
{
    struct node *temp = head;

    while (temp != NULL)
    {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }

    printf("NULL\n");
}

int main()
{
    struct node *head;
    struct node *second;
    struct node *third;
    int value;

    head = malloc(sizeof(struct node));
    second = malloc(sizeof(struct node));
    third = malloc(sizeof(struct node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    printf("Linked list before deletion:\n");
    display(head);

    printf("Enter element to delete: ");
    scanf("%d", &value);

    deleteElement(&head, value);

    printf("Linked list after deletion:\n");
    display(head);

    return 0;
}



```

Output:

<img width="757" height="186" alt="image" src="https://github.com/user-attachments/assets/7de84d1f-3634-4255-bb9b-a700448be2bf" />






Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





