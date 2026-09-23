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

int main()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    switch(n)
    {
        case 1:
            printf("one");
            break;

        case 2:
            printf("two");
            break;

        case 3:
            printf("three");
            break;

        case 4:
            printf("four");
            break;

        case 5:
            printf("five");
            break;

        case 6:
            printf("six");
            break;

        case 7:
            printf("seven");
            break;

        case 8:
            printf("eight");
            break;

        case 9:
            printf("nine");
            break;

        default:
            printf("Greater than 9");
    }

    return 0;
}



```




Output:


<img width="753" height="77" alt="image" src="https://github.com/user-attachments/assets/cbb7f4d0-3936-4f42-8760-6fd1d09cd492" />







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

int main()
{
    char a[50];
    int i, j, c;

    printf("Enter the numbers: ");
    scanf("%s", a);

    for(i = 0; i <= 3; i++)
    {
        c = 0;

        for(j = 0; a[j] != '\0'; j++)
        {
            if(a[j] == i + '0')
            {
                c++;
            }
        }

        printf("%d ", c);
    }

    return 0;
}




```




Output:


<img width="757" height="82" alt="image" src="https://github.com/user-attachments/assets/7eb741e2-f774-4fd9-bf99-2069d0e7b920" />







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
#include <string.h>

void swap(char *a, char *b)
{
    char temp = *a;
    *a = *b;
    *b = temp;
}

void sort(char s[], int n)
{
    int i, j;

    for(i = 0; i < n - 1; i++)
    {
        for(j = i + 1; j < n; j++)
        {
            if(s[i] > s[j])
            {
                swap(&s[i], &s[j]);
            }
        }
    }
}

int nextPermutation(char s[], int n)
{
    int i, j;

    i = n - 2;

    while(i >= 0 && s[i] >= s[i + 1])
    {
        i--;
    }

    if(i < 0)
    {
        return 0;
    }

    j = n - 1;

    while(s[j] <= s[i])
    {
        j--;
    }

    swap(&s[i], &s[j]);

    i++;
    j = n - 1;

    while(i < j)
    {
        swap(&s[i], &s[j]);
        i++;
        j--;
    }

    return 1;
}

int main()
{
    char s[100];
    int n;

    printf("Enter a string: ");
    scanf("%99s", s);

    n = strlen(s);

    sort(s, n);

    printf("Permutations:\n");

    do
    {
        printf("%s\n", s);
    }
    while(nextPermutation(s, n));

    return 0;
}



```




Output:


<img width="518" height="384" alt="image" src="https://github.com/user-attachments/assets/5d83f7f0-a902-453b-8b82-6342e9f0b907" />







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

int main()
{
    int n, i, j, len, min;

    printf("Enter n: ");
    scanf("%d", &n);

    len = n * 2 - 1;

    for(i = 0; i < len; i++)
    {
        for(j = 0; j < len; j++)
        {
            min = i;

            if(j < min)
                min = j;

            if(len - 1 - i < min)
                min = len - 1 - i;

            if(len - 1 - j < min)
                min = len - 1 - j;

            printf("%d ", n - min);
        }

        printf("\n");
    }

    return 0;
}





```




Output:


<img width="753" height="184" alt="image" src="https://github.com/user-attachments/assets/2c604677-e7ff-42b5-9c52-047f1cab7ef8" />







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

long long int square()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    return n * n;
}

int main()
{
    int result;

    result = square();

    printf("Square = %lld\n", result);

    return 0;
}


```




Output:


<img width="754" height="159" alt="image" src="https://github.com/user-attachments/assets/c29a6630-71a9-4798-ad6b-65ffd3515348" />







Result:
Thus, the program is verified successfully



























