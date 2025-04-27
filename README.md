# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, width, area;  
    float *ptr_length = &length;
    float *ptr_area = &area;    

   
    printf("Enter the length of the rectangle: ");
    scanf("%f", ptr_length);
    printf("Enter the width of the rectangle: ");
    scanf("%f", ptr_width);  
    *ptr_area = (*ptr_length) * (*ptr_width);  
    printf("The area of the rectangle is: %.2f\n", *ptr_area);  
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/26383866-fe24-4179-ab9e-3c3bf8cf2d76)



## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>  // For malloc() and free()

int main() {
    // Dynamically allocate memory for the string "WELCOME"
    char *str = (char *)malloc(8 * sizeof(char));  // 8 characters: W, E, L, C, O, M, E, '\0'

    // Check if malloc returned NULL (in case memory allocation fails)
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1; // Exit the program with error code
    }

    // Assign the string "WELCOME" to the allocated memory
    str[0] = 'W';
    str[1] = 'E';
    str[2] = 'L';
    str[3] = 'C';
    str[4] = 'O';
    str[5] = 'M';
    str[6] = 'E';
    str[7] = '\0';  // Null-terminate the string

    // Print the string
    printf("%s\n", str);

    // Free the allocated memory
    free(str);

    return 0;
}
```
## OUTPUT

![image](https://github.com/user-attachments/assets/8aadde51-3cfd-4e2b-8ffe-e73b108e93ad)


## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <string.h>

struct Student {
    char name[50];
    int rollNumber;
    float marks;
};

int main() {
    int n;

   
    printf("Enter the number of students: ");
    scanf("%d", &n);

    
    struct Student students[n];

    
    for (int i = 0; i < n; i++) {
        printf("\nEnter details for student %d:\n", i + 1);
        
        printf("Enter name: ");
        getchar(); 
        fgets(students[i].name, sizeof(students[i].name), stdin); 
        students[i].name[strcspn(students[i].name, "\n")] = '\0'; 
        printf("Enter roll number: ");
        scanf("%d", &students[i].rollNumber);

        printf("Enter marks: ");
        scanf("%f", &students[i].marks);
    }

   
    printf("\nStudent Information:\n");
    for (int i = 0; i < n; i++) {
        printf("\nStudent %d:\n", i + 1);
        printf("Name: %s\n", students[i].name);
        printf("Roll Number: %d\n", students[i].rollNumber);
        printf("Marks: %.2f\n", students[i].marks);
    }

    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/61cef739-fd61-449d-b929-56bafd1ad049)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>


struct Employee {
    char name[50];
    int basic_salary;
    int house_rent_allowance;
    int medical_allowance;
    int gross_salary;
};

int main() {
    struct Employee emp[3]; 
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Employee %d:\n", i + 1);
        printf("Enter name: ");
        getchar();  
        fgets(emp[i].name, sizeof(emp[i].name), stdin); 
        emp[i].name[strcspn(emp[i].name, "\n")] = '\0'; 
       printf("Enter Basic Salary: ");
        scanf("%d", &emp[i].basic_salary);

        printf("Enter House Rent Allowance: ");
        scanf("%d", &emp[i].house_rent_allowance);

        printf("Enter Medical Allowance: ");
        scanf("%d", &emp[i].medical_allowance);

      
        emp[i].gross_salary = emp[i].basic_salary + emp[i].house_rent_allowance + emp[i].medical_allowance;

        printf("\n");
    }

   
    printf("\nEmployee Details:\n");
    for (int i = 0; i < 3; i++) {
        printf("Employee %d: \n", i + 1);
        printf("Name: %s\n", emp[i].name);
        printf("Basic Salary: %d\n", emp[i].basic_salary);
        printf("House Rent Allowance: %d\n", emp[i].house_rent_allowance);
        printf("Medical Allowance: %d\n", emp[i].medical_allowance);
        printf("Gross Salary: %d\n\n", emp[i].gross_salary);
    }

    return 0;
}
```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/d812af54-50e0-4956-8b36-cfdc0f72aed2)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>


struct Student {
    char name[50];
    int marks[5]; 
    int total;
    float average;
};

int main() {
    struct Student students[3];  
    for (int i = 0; i < 3; i++) {
        printf("Enter details for Student %d:\n", i + 1);

        printf("Enter name: ");
        getchar();  
        fgets(students[i].name, sizeof(students[i].name), stdin); 
        students[i].name[strcspn(students[i].name, "\n")] = '\0';  
        students[i].total = 0;
        printf("Enter marks for 5 subjects:\n");
        for (int j = 0; j < 5; j++) {
            printf("Subject %d: ", j + 1);
            scanf("%d", &students[i].marks[j]);
            students[i].total += students[i].marks[j];  
        }

       
        students[i].average = students[i].total / 5.0;

        printf("\n");
    }

    
    printf("\nStudent Details:\n");
    for (int i = 0; i < 3; i++) {
        printf("Student %d:\n", i + 1);
        printf("Name: %s\n", students[i].name);
        printf("Total Marks: %d\n", students[i].total);
        printf("Average Marks: %.2f\n\n", students[i].average);
    }

    return 0;
}
```

## OUTPUT

 ![image](https://github.com/user-attachments/assets/ef15b451-484f-4beb-a428-8cd1deb405bd)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


