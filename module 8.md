EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    switch (n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("Greater than 13\n");
    }

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/1ca0dd4f-4d4f-434b-96eb-4ba8c91fd35a)



Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>
int main() {
    char a[50];
    int h, i, c;
    printf("Enter the string containing digits: ");
    scanf("%s", a);
    for (h = 0; h <= 3; h++) {
        c = 0;
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) {
                c++;
            }
        }
        printf("%d ", c);
    }

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/28d43d5a-ec45-4560-a428-d934c002d2d0)



Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char **x, char **y) {
    char *temp = *x;
    *x = *y;
    *y = temp;
}
void sort(char **arr, int n) {
    int i, j;
    for (i = 0; i < n-1; i++) {
        for (j = i+1; j < n; j++) {
            if (strcmp(arr[i], arr[j]) > 0) {
                swap(&arr[i], &arr[j]);
            }
        }
    }
}
int next_permutation(char **arr, int n) {
    int i = n - 2;
    while (i >= 0 && strcmp(arr[i], arr[i+1]) >= 0)
        i--;
    if (i < 0) return 0;

    int j = n - 1;
    while (strcmp(arr[i], arr[j]) >= 0)
        j--;
    swap(&arr[i], &arr[j]);
    int left = i+1, right = n-1;
    while (left < right) {
        swap(&arr[left], &arr[right]);
        left++;
        right--;
    }
    return 1;
}

int main() {
    char **s;
    int n, i;
    printf("Enter the number of strings: ");
    scanf("%d", &n);
    s = (char **)malloc(n * sizeof(char *));
    for (i = 0; i < n; i++) {
        s[i] = (char *)malloc(100 * sizeof(char)); 
    }

    printf("Enter the strings:\n");
    for (i = 0; i < n; i++) {
        scanf("%s", s[i]);
    }
    sort(s, n);

    printf("Permutations in lexicographical order:\n");

    do {
        for (i = 0; i < n; i++) {
            printf("%s ", s[i]);
        }
        printf("\n");
    } while (next_permutation(s, n));
    for (i = 0; i < n; i++) {
        free(s[i]);
    }
    free(s);

    return 0;
}
```



Output:


![image](https://github.com/user-attachments/assets/ffaf098a-4ffc-47c0-b4b5-af080b2e8822)



Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>
int min(int a, int b) {
    return (a < b) ? a : b;
}
int main() {
    int n, i, j, len, value;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    len = n * 2 - 1;
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            int min_distance = min(min(i, j), min(len - 1 - i, len - 1 - j));
            value = n - min_distance;
            printf("%d ", value);
        }
        printf("\n");
    }

    return 0;
}
```




Output:

![image](https://github.com/user-attachments/assets/d39b9b0c-44ed-4032-8f53-7d5201db44a6)







Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
 ```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num; 
}
int main() {
    int result;
    result = square();
    printf("Square of the number is: %d\n", result);

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/6a7f457d-ae45-43a2-a268-8bf065e6517b)


Result:
Thus, the program is verified successfully



























