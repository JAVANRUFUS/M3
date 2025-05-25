# EX-11-EMI-CALCULATOR

## AIM

To write a program to prepare EMI calculator using function without return type and with arguments.

## ALGORITHM

1.	Start the program.
2.	Read principal amount, rate of interest and months.
3.	Pass these values as arguments to function.
4.	Calculate EMI using the formula, amt=(prpow(1+r,t))/(pow(1+r,t)-1)
5.	Display the result.
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <math.h>

// Function declaration (no return, with arguments)
void calculateEMI(float principal, float rate, int time);

int main() {
    float principal, rate;
    int time;

    // Input loan details
    printf("Enter loan amount (principal): ");
    scanf("%f", &principal);

    printf("Enter annual interest rate (in %%): ");
    scanf("%f", &rate);

    printf("Enter loan tenure (in years): ");
    scanf("%d", &time);

    // Function call
    calculateEMI(principal, rate, time);

    return 0;
}

// Function definition
void calculateEMI(float principal, float rate, int time) {
    float monthlyRate;
    int months;
    float emi;

    // Convert annual rate to monthly and time to months
    monthlyRate = rate / (12 * 100); // annual % to monthly decimal
    months = time * 12;

    // EMI formula: EMI = P * r * (1 + r)^n / ((1 + r)^n - 1)
    emi = principal * monthlyRate * pow(1 + monthlyRate, months) / (pow(1 + monthlyRate, months) - 1);

    // Display result
    printf("\n--- EMI Calculation ---\n");
    printf("Loan Amount: %.2f\n", principal);
    printf("Annual Interest Rate: %.2f%%\n", rate);
    printf("Loan Tenure: %d years (%d months)\n", time, months);
    printf("Monthly EMI: %.2f\n", emi);
}

```

## OUTPUT
![Screenshot 2025-05-25 132644](https://github.com/user-attachments/assets/bf9e72dc-30c9-430b-b614-c7950754b9e6)

## RESULT

Thus the program to prepare EMI calculator using function without return type with arguments has been executed successfully
 
 


# EX-12-FIBONACCI-SERIES
## AIM
To write a C program to generate the Fibonacci series for the value 6.

## ALGORITHM
1.	Start the program.
2.	Read number of terms to display.
3.	Add the previous two terms and store it in new term.
4.	Assign 2nd term to 1st term and 3rd term to 2nd term.
5.	Repeat steps 3 and 4 n number of times.
6.	Display the result.
7.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int n = 6; // number of terms
    int first = 0, second = 1, next;

    printf("Fibonacci Series for %d terms:\n", n);

    for (int i = 1; i <= n; i++) {
        printf("%d ", first);
        next = first + second;
        first = second;
        second = next;
    }

    printf("\n");
    return 0;
}

```
## OUTPUT
![Screenshot 2025-05-25 132832](https://github.com/user-attachments/assets/110d9368-a27e-4753-8e99-ba152178678d)

## RESULT
Thus the program to generate the Fibonacci series for the value 6 has been executed successfully.
 
 


# EX-13-ONE-DIMENSIONAL-ARRAY
## AIM
To write a C program to read n elements as input and print the last element of the array.

## ALGORITHM
1.	Start the program.
2.	Read a variable.
3.	Read the array values n number of times.
4.	Print the last element.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int n;

    // Input size of array
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // Validate input
    if (n <= 0) {
        printf("Invalid size. Number of elements must be positive.\n");
        return 1;
    }

    int arr[n];

    // Input elements
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Output the last element
    printf("The last element is: %d\n", arr[n - 1]);

    return 0;
}

```

## OUTPUT
![Screenshot 2025-05-25 132956](https://github.com/user-attachments/assets/4bba7ce6-1290-45e3-8660-304d45f2d859)


## RESULT
Thus the program to read n elements as input and print the last element of the array has been executed successfully.
 
 


# EX-14-POSITIVE-ARRAY-ELEMENTS
## AIM
To write a C Program to count total number of positive elements in an array.

## ALGORITHM
1.	Start the program.
2.	Read a variable.
3.	Read the array values n number of times.
4.	If the array value can be divided by 2 then increment count by 1.
5.	Display result.
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int n, count = 0;

    // Input array size
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    // Validate size
    if (n <= 0) {
        printf("Invalid size. Please enter a positive number.\n");
        return 1;
    }

    int arr[n];

    // Input elements
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);

        // Count if positive
        if (arr[i] > 0) {
            count++;
        }
    }

    // Display result
    printf("Total number of positive elements: %d\n", count);

    return 0;
}

```

## OUTPUT
![Screenshot 2025-05-25 133212](https://github.com/user-attachments/assets/4a9cc298-06a2-40b3-ae9d-4cb56e4af003)

## RESULT
Thus the program to count total number of positive elements in an array has been executed successfully.


# EX -15 - Replace All Even Elements With 'E' In One Dimensional Array

## Aim:
To write a C program to replace all even elements with 'E' in one dimensional array

## Algorithm:
1.	Input the array:
  Read the size of the array.
  Input the elements of the array.
2.	Iterate through the array:
 	For each element of the array, check if the element is even (i.e., if the element modulo 2 equals 0).
3.	Replace even elements with 'E':
     If an element is even, replace that element with the character 'E'.
4.	Output the updated array:
 Print the updated array after replacements.

## Program:
```#include <stdio.h>

int main() {
    int n;

    // Input number of elements
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid size. Must be positive.\n");
        return 1;
    }

    int arr[n];

    // Input elements
    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    // Output array with 'E' for even numbers
    printf("Modified array:\n");
    for (int i = 0; i < n; i++) {
        if (arr[i] % 2 == 0) {
            printf("E ");
        } else {
            printf("%d ", arr[i]);
        }
    }

    printf("\n");
    return 0;
}
```
## Output:
 ![Screenshot 2025-05-25 133517](https://github.com/user-attachments/assets/fe5325aa-3fb3-4cb2-90df-2df5c9576f1d)



## Result:

Thus, the program to replace all even elements with 'E' in one dimensional array was verified successfully.



