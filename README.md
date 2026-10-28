# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char text[100];
    int key[3][3];
    int i, j, k, len, value;
    int block[3];

    printf("Enter plaintext (letters only): ");
   scanf("%49[^\n]", text);

    printf("Enter the 3x3 key matrix:\n");
    for (i = 0; i < 3; i++)
    {
        for (j = 0; j < 3; j++)
        {
            scanf("%d", &key[i][j]);
        }
    }

    len = strlen(text);

    for (i = 0; i < len; i++)
        text[i] = toupper((unsigned char)text[i]);

    while (len % 3 != 0)
        text[len++] = 'X';

    text[len] = '\0';

    printf("Ciphertext: ");

    for (i = 0; i < len; i += 3)
    {
        for (j = 0; j < 3; j++)
            block[j] = text[i + j] - 'A';

        for (j = 0; j < 3; j++)
        {
            value = 0;

            for (k = 0; k < 3; k++)
                value += key[j][k] * block[k];

            value = ((value % 26) + 26) % 26;
            printf("%c", value + 'A');
        }
    }

    printf("\n");

    return 0;
}
```

## OUTPUT
<img width="1530" height="778" alt="image" src="https://github.com/user-attachments/assets/7ba5259a-a846-4211-8a2f-f40d10bac030" />



## RESULT
Thus, the C program to implement the Hill Cipher substitution technique was written and executed successfully.
