EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
```
#include <stdio.h>
#include <string.h>

// Structure to store name and age
struct eligible {
    char name[50];
    int age;
};

int main() {
    int i, n;

    // Ask how many people to check
    printf("Enter the number of persons: ");
    scanf("%d", &n);

    // Declare an array of structures
    struct eligible e[n];

    // Input details for each person
    for(i = 0; i < n; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", e[i].name);

        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &e[i].age);
    }

    // Check eligibility and display results
    printf("\n--- VACCINE ELIGIBILITY STATUS ---\n");
    for(i = 0; i < n; i++) {
        printf("\nName: %s", e[i].name);
        printf("\nAge: %d", e[i].age);

        if(e[i].age > 6) {
            printf("\nVaccine Eligibility: Yes\n");
        } else {
            printf("\nVaccine Eligibility: No\n");
        }
    }

    return 0;
}
```



Output:

![image](https://github.com/user-attachments/assets/e7d9da03-acb3-41b4-8501-d60040361852)



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

```
#include <stdio.h>

// Step 1: Define structure 'numbers' with members a and b
struct numbers {
    int a;
    int b;
};

// Function that takes a structure as argument and returns a structure
struct numbers add(struct numbers n) {
    struct numbers result;
    result.a = n.a + n.b; // sum stored in result.a
    result.b = 0;         // optional, no use here
    return result;
}

int main() {
    struct numbers n, sum;

    // Step 3 & 4: Input values for a and b
    printf("Enter two numbers:\n");
    printf("a = ");
    scanf("%d", &n.a);
    printf("b = ");
    scanf("%d", &n.b);

    // Step 5: Call add function
    sum = add(n);

    // Step 6: Print the result
    printf("Sum = %d\n", sum.a);

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/cc6e0b6c-194b-4610-bce3-ec74bb1f520d)


Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```#include <stdio.h>

int main() {
    FILE *p;
    char name[100];

    // Step 4: Read file name from user
    printf("Enter the file name to create: ");
    scanf("%s", name);

    // Step 5: Inform user
    printf("Creating file: %s\n", name);

    // Step 6: Open file in write mode
    p = fopen(name, "w");

    if (p == NULL) {
        // File opening failed
        printf("Error: Unable to create the file %s\n", name);
        return 1; // Exit with error
    }

    // Step 7: Success message
    printf("File '%s' opened successfully in write mode.\n", name);

    // Step 8: Close the file
    fclose(p);

    // Step 9: Confirm file is closed
    printf("File '%s' closed successfully.\n", name);

    return 0; // Step 10: End of program
}
```



Output:

![image](https://github.com/user-attachments/assets/6bf77ae0-4f3e-4c98-9927-65cd2b176407)

Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
```
#include <stdio.h>

int main() {
    FILE *p;
    char name[100], text[200];
    int num, i;

    // Step 4: Read file name and number of strings from user
    printf("Enter the file name to write into: ");
    scanf("%s", name);

    printf("Enter the number of lines to insert: ");
    scanf("%d", &num);

    // Step 5: Open file in write mode
    p = fopen(name, "w");

    if (p == NULL) {
        printf("Error: Unable to open or create the file %s\n", name);
        return 1;
    }

    // Step 6: Success message
    printf("File '%s' opened successfully for writing.\n", name);

    // Step 7: Loop to get text input and write to file
    printf("Enter the text lines:\n");
    for(i = 0; i < num; i++) {
        printf("Line %d: ", i + 1);
        getchar(); // Clear newline character from buffer
        fgets(text, sizeof(text), stdin); // Read full line including spaces
        fputs(text, p); // Write line to file
    }

    // Step 8: Close the file
    fclose(p);

    // Step 9: Success message
    printf("Text successfully written to '%s'.\n", name);

    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/f3f81be4-4493-4b91-8e2f-bbaffcf8137b)


Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
```
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define structure for subject details
struct Subject {
    char name[50];
    int marks;
};

int main() {
    struct Subject *s;
    int n, i;

    // Step 2: Input number of subjects
    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // Step 3 & 4: Dynamically allocate memory for n subjects
    s = (struct Subject *)malloc(n * sizeof(struct Subject));

    // Step 5: Check if memory allocation was successful
    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Step 6 & 7: Input subject details
    printf("\nEnter subject name and marks:\n");
    for (i = 0; i < n; i++) {
        printf("\nSubject %d Name: ", i + 1);
        scanf("%s", s[i].name);
        printf("Subject %d Marks: ", i + 1);
        scanf("%d", &s[i].marks);
    }

    // Step 8 & 9: Display subject details
    printf("\n--- Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject %d: %s, Marks: %d\n", i + 1, s[i].name, s[i].marks);
    }

    // Step 10 & 11: Free allocated memory
    free(s);

    // Step 12 & 13: End program
    return 0;
}
```




Output:

![image](https://github.com/user-attachments/assets/4cea1360-2d56-498d-9952-28863f77d1a2)

Result:
Thus, the program is verified successfully
