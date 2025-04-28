# EX-26 - Area of Rectangle Using Pointer  
## AIM:  
To write a C Program to find area of rectangle using pointer.

## PROGRAM:
```c
#include <stdio.h>

int main() {
    int length, breadth, area;
    int *ptrLength, *ptrBreadth;

    printf("Enter the length of the rectangle: ");
    scanf("%d", &length);
    printf("Enter the breadth of the rectangle: ");
    scanf("%d", &breadth);

    ptrLength = &length;
    ptrBreadth = &breadth;

    area = (*ptrLength) * (*ptrBreadth);

    printf("Area of Rectangle = %d\n", area);
    return 0;
}
```

## OUTPUT:
```
Enter the length of the rectangle: 5
Enter the breadth of the rectangle: 6
Area of Rectangle = 30
```

## RESULT:  
Thus the program to find area of rectangle using pointer has been executed successfully.


# EX-27 - Dynamic Memory Allocation  
## AIM:  
To write a C Program to print 'WELCOME' using malloc() and free().

## PROGRAM:
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char)); // Allocate memory for "WELCOME" + '\0'
    if(str == NULL) {
        printf("Memory not allocated.\n");
        return 1;
    }

    strcpy(str, "WELCOME");

    printf("%s\n", str);

    free(str); // Free the allocated memory

    return 0;
}
```

## OUTPUT:
```
WELCOME
```

## RESULT:  
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully.


# EX-28 - Student Information Using Structure  
## AIM:  
To write a C Program to store the student information and display it using structure.

## PROGRAM:
```c
#include <stdio.h>

struct Student {
    char name[50];
    int rollNo;
    float marks;
};

int main() {
    struct Student s;

    printf("Enter name: ");
    scanf("%s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.rollNo);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll No: %d\n", s.rollNo);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}
```

## OUTPUT:
```
Enter name: John
Enter roll number: 101
Enter marks: 87.5

Student Information:
Name: John
Roll No: 101
Marks: 87.50
```

## RESULT:  
Thus the program to store the student information and display it using structure has been executed successfully.


# EX-29 - Employee Structure Salary Calculation  
## AIM:  
To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## PROGRAM:
```c
#include <stdio.h>

struct Employee {
    char name[50];
    int id;
    float basicSalary, hra, da, grossSalary;
};

int main() {
    struct Employee e[3];
    int i;

    for(i = 0; i < 3; i++) {
        printf("\nEnter details for Employee %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", e[i].name);
        printf("ID: ");
        scanf("%d", &e[i].id);
        printf("Basic Salary: ");
        scanf("%f", &e[i].basicSalary);

        e[i].hra = 0.2 * e[i].basicSalary;
        e[i].da = 0.1 * e[i].basicSalary;
        e[i].grossSalary = e[i].basicSalary + e[i].hra + e[i].da;
    }

    printf("\nEmployee Details:\n");
    for(i = 0; i < 3; i++) {
        printf("Name: %s, ID: %d, Gross Salary: %.2f\n", e[i].name, e[i].id, e[i].grossSalary);
    }

    return 0;
}
```

## OUTPUT:
```
Enter details for Employee 1:
Name: Alice
ID: 101
Basic Salary: 20000

Enter details for Employee 2:
Name: Bob
ID: 102
Basic Salary: 25000

Enter details for Employee 3:
Name: Charlie
ID: 103
Basic Salary: 30000

Employee Details:
Name: Alice, ID: 101, Gross Salary: 26000.00
Name: Bob, ID: 102, Gross Salary: 32500.00
Name: Charlie, ID: 103, Gross Salary: 39000.00
```

## RESULT:  
Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure has been executed successfully.


# EX-30 - Students Marks Total & Average Using Structure  
## AIM:  
Create a C program to calculate the total and average of student using structure.

## PROGRAM:
```c
#include <stdio.h>

struct Student {
    int rollno;
    char name[10];
    int subject[5];
    int total;
};

int main() {
    struct Student s[2];
    int i, j;
    float average;

    for(i = 0; i < 2; i++) {
        printf("\nEnter details for Student %d\n", i + 1);
        printf("Enter Roll Number: ");
        scanf("%d", &s[i].rollno);
        printf("Enter Name: ");
        scanf("%s", s[i].name);

        printf("Enter 5 subject marks:\n");
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].subject[j]);
        }
    }

    for(i = 0; i < 2; i++) {
        s[i].total = 0;
        for(j = 0; j < 5; j++) {
            s[i].total += s[i].subject[j];
        }
        average = s[i].total / 5.0;
        printf("\nStudent %d (%s):\n", i + 1, s[i].name);
        printf("Total Marks = %d\n", s[i].total);
        printf("Average Marks = %.2f\n", average);
    }

    return 0;
}
```

## OUTPUT:
```
Enter details for Student 1
Enter Roll Number: 1
Enter Name: John
Enter 5 subject marks:
75 85 65 90 80

Enter details for Student 2
Enter Roll Number: 2
Enter Name: Jane
Enter 5 subject marks:
88 92 76 81 79

Student 1 (John):
Total Marks = 395
Average Marks = 79.00

Student 2 (Jane):
Total Marks = 416
Average Marks = 83.20
```

## RESULT:  
Thus the C program to calculate the total and average of student using structure has been executed successfully.
