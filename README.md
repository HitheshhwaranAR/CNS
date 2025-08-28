## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
#include <stdio.h>
#include <ctype.h> // for isupper(), islower()

void encrypt(char text[], int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isupper(text[i])) {
            text[i] = (text[i] - 'A' + shift) % 26 + 'A';
        }
        else if (islower(text[i])) {
            text[i] = (text[i] - 'a' + shift) % 26 + 'a';
        }
    }
}
// Function to decrypt text
void decrypt(char text[], int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isupper(text[i])) {
            text[i] = (text[i] - 'A' - shift + 26) % 26 + 'A';
        }
        else if (islower(text[i])) {
            text[i] = (text[i] - 'a' - shift + 26) % 26 + 'a';
        }
    }
}

int main() {
    char text[100];
    int shift;

    printf("Enter a message: ");
    fgets(text, sizeof(text), stdin); // read input including spaces
    printf("Enter shift key: ");
    scanf("%d", &shift);

    encrypt(text, shift);
    printf("Encrypted text: %s", text);

    decrypt(text, shift);
    printf("Decrypted text: %s", text);

    return 0;
}
```


OUTPUT :-
<img width="1702" height="1035" alt="Screenshot 2025-08-28 140002" src="https://github.com/user-attachments/assets/fd9fa641-7187-459c-b82a-d73a7ff5e594" />
