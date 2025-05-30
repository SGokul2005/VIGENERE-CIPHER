## EX.4 VIGENERE CIPHER
# Name: GOKUL S
# Reg.no: 21223040051
# Vigenere Cipher:
Vigenere Cipher using with different key values.
# AIM:
To develop a simple C program to implement Vigenere Cipher.
# DESIGN STEPS:
Step 1:
Design of Vigenere Cipher algorithnm
Step 2:
Implementation using C or pyhton code
Step 3:
Testing algorithm with different key values. ALGORITHM DESCRIPTION: The Vigenere cipher is a
method of encrypting alphabetic text by using a series of different Caesar ciphers based on the letters
of a keyword. It is a simple form of polyalphabetic substitution.To encrypt, a table of alphabets can be
used, termed a Vigenere square, or Vigenere table. It consists of the alphabet written out 26 times in
different rows, each alphabet shifted cyclically to the left compared to the previous alphabet,
corresponding to the 26 possible Caesar ciphers. At different points in the encryption process, the
cipher uses a different alphabet from one of the rows used. The alphabet at each point depends on a
repeating keyword.
# PROGRAM:
```
#include <stdio.h>
#include <string.h>
// Function to perform Vigenère encryption
void vigenereEncrypt(char *text, const char *key) {
int textLen = strlen(text);
int keyLen = strlen(key);
for (int i = 0; i < textLen; i++) {
char c = text[i];
if (c >= 'A' && c <= 'Z') {
text[i] = ((c - 'A' + key[i % keyLen] - 'A') % 26) + 'A';
} else if (c >= 'a' && c <= 'z') {
text[i] = ((c - 'a' + key[i % keyLen] - 'A') % 26) + 'a';
}
}
}
// Function to perform Vigenère decryption
void vigenereDecrypt(char *text, const char *key) {
int textLen = strlen(text);
int keyLen = strlen(key);
for (int i = 0; i < textLen; i++) {
char c = text[i];
if (c >= 'A' && c <= 'Z') {
text[i] = ((c - 'A' - (key[i % keyLen] - 'A') + 26) % 26) + 'A';
} else if (c >= 'a' && c <= 'z') {
text[i] = ((c - 'a' - (key[i % keyLen] - 'A') + 26) % 26) + 'a';
}
}
}
int main() {
char key[100], message[100];
// Get user input
printf("Enter the key (uppercase letters only): ");
scanf("%s", key);
printf("Enter the message: ");
scanf(" %[^\n]", message); // Read full line including spaces
// Encrypt the message
vigenereEncrypt(message, key);
printf("Encrypted Message: %s\n", message);
// Decrypt the message back to the original
vigenereDecrypt(message, key);
printf("Decrypted Message: %s\n", message);
return 0;
}
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/19ff0c4c-9de3-4cda-8bab-6282397e1dce)

Simulating Vigenere Cipher:
Input Message: GOKUL
Key Message: WRITE
Encrypted Message: CFSNP
Decrypted Message: GOKUL
# RESULT:
The program is executed successfully
