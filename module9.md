EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>

#define MAX 5 

int stack[MAX];
int top = -1;
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed into stack.\n", value);
    }
}

void pop() {
    if (top == -1) {
        printf("Stack Underflow! No elements to pop.\n");
    } else {
        printf("%d popped from stack.\n", stack[top]);
        top--;
    }
}
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n*** Stack Menu ***\n");
        printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice! Please enter between 1-4.\n");
        }
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/23954032-05e6-42b1-95e2-89f12dd2cedd)



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

#define MAX 5 

float stack[MAX]; 
int top = -1;     

// Function to push a floating-point number into the stack
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed into the stack.\n", value);
    }
}

int main() {
    int n, i;
    float value;

    printf("Enter the number of elements to push (max %d): ", MAX);
    scanf("%d", &n);

    if (n > MAX) {
        printf("Cannot push more than %d elements.\n", MAX);
        return 1;
    }

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        push(value);
    }

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/fadc257d-ad52-4bd6-bb4d-0825e0d37042)




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
#define MAX 5 
int queue[MAX];
int front = -1, rear = -1;
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot enqueue %d\n", value);
    } else {
        if (front == -1) // First element inserted
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d enqueued into the queue.\n", value);
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/38c92f9f-89c9-42c4-84ab-6e06c31c2763)



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
#define MAX 5 
float queue[MAX]; 
int front = -1, rear = -1; 
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
    } else {
        if (front == -1) 
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

int main() {
    int n;
    float value;
    printf("Enter the number of elements to insert into the queue (max %d): ", MAX);
    scanf("%d", &n);

    if (n > MAX) {
        printf("Cannot insert more than %d elements.\n", MAX);
        return 1; 
    }
    for (int i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value); 
    }

    return 0;
}
```

Output:
![image](https://github.com/user-attachments/assets/5a4a368b-91e7-432c-8398-a8c2a015830b)


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

#define MAX 5 

int queue[MAX];
int front = -1, rear = -1;
void dequeue() {
    if (front == -1) {
        printf("Queue is empty! No elements to delete.\n");
    } else {
        printf("Deleted %d from the queue.\n", queue[front]);
        front++; 
        if (front > rear) {
            front = rear = -1; // Reset the queue if it's empty
            printf("Queue is now empty.\n");
        }
    }
}

int main() {
    rear = 2; front = 0; // Setting up a sample queue
    queue[0] = 10; queue[1] = 20; queue[2] = 30;
    printf("Before Deletion:\n");
    printf("Front: %d, Rear: %d\n", front, rear);
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");
    dequeue();
    printf("\nAfter Deletion:\n");
    printf("Front: %d, Rear: %d\n", front, rear);
    for (int i = front; i <= rear; i++) {
        printf("%d ", queue[i]);
    }
    printf("\n");

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/2a7767ca-44d3-4bee-8e7e-a8c76fe007ee)



Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
