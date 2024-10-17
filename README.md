
# EXP 1 Caeser Cipher

Caeser Cipher using with different key values
## AIM:
To encrypt and decrypt the given message by using Ceaser Cipher encryption algorithm.
## DESIGN STEPS:
Step 1:
Design of Caeser Cipher algorithnm
Step 2:
Implementation using C or pyhton code
Step 3:
1. In Ceaser Cipher each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.
    For example, with a left shift of 3, D would be replaced by A, E would become B, and so on.
2. The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the
    scheme, A = 0, B = 1, Z = 25.
3. Encryption of a letter x by a shift n can be described mathematically as, En(x) = (x + n) mod26
    Decryption is performed similarly, Dn (x)=(x - n) mod26
```
## PROGRAM:

CaearCipher.

#include <stdio.h>
#include <string.h>

void encrypt(char message[], int shift) {
    char ch;
    for (int i = 0; message[i] != '\0'; ++i) {
        ch = message[i];
        if (ch >= 'a' && ch <= 'z') {
            ch = ch + shift;
            if (ch > 'z') {
                ch = ch - 'z' + 'a' - 1;
            }
            message[i] = ch;
        } else if (ch >= 'A' && ch <= 'Z') {
            ch = ch + shift;
            if (ch > 'Z') {
                ch = ch - 'Z' + 'A' - 1;
            }
            message[i] = ch;
        }
    }
    printf("Encrypted message: %s\n", message);
}

void decrypt(char message[], int shift) {
    char ch;
    for (int i = 0; message[i] != '\0'; ++i) {
        ch = message[i];
        if (ch >= 'a' && ch <= 'z') {
            ch = ch - shift;
            if (ch < 'a') {
                ch = ch + 'z' - 'a' + 1;
            }
            message[i] = ch;
        } else if (ch >= 'A' && ch <= 'Z') {
            ch = ch - shift;
            if (ch < 'A') {
                ch = ch + 'Z' - 'A' + 1;
            }
            message[i] = ch;
        }
    }
    printf("Decrypted message: %s\n", message);
}

int main() {
    printf("  ***Caeser Cipher***\n");
    char message[100];
    int shift;

    printf("Enter a message: ");
    fgets(message, sizeof(message), stdin);  // Correct use of fgets

    printf("Enter shift amount: ");
    scanf("%d", &shift);

    // Make a copy of the message to decrypt later
    char encrypted_message[100];
    strcpy(encrypted_message, message);

    encrypt(encrypted_message, shift);
    decrypt(encrypted_message, shift);

    return 0;
}
```

OUTPUT:

![Screenshot 2024-10-07 085724](https://github.com/user-attachments/assets/e9211305-82b2-48e9-8183-5362206358ac)


RESULT:

The program for the Caeser Cipher is executed successfully.
