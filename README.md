# EX-NO-7-Implement-DES-Encryption-and-Decryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
### Encryption:
```c
#include <stdio.h>
#include <string.h>

// Function to perform a simple encryption using XOR
void desEncrypt(const char *plaintext, const char *key, char *ciphertext) {
    for (int i = 0; i < 8; i++) {
        ciphertext[i] = plaintext[i] ^ key[i];
    }
}

int main() {
    char plaintext[8] = "HELLO123"; // 8-byte plaintext (must be 8 bytes)
    char key[8] = "KEY12345";       // 8-byte key
    char ciphertext[8];

    printf("Original Text: %s\n", plaintext);

    // Encrypt the plaintext
    desEncrypt(plaintext, key, ciphertext);

    // Print the ciphertext in hexadecimal format
    printf("Encrypted Text (Hex): ");
    for (int i = 0; i < 8; i++) {
        printf("%02X ", (unsigned char)ciphertext[i]);
    }
    printf("\n");

    return 0;
}
```
### Decryption:
```c
#include <stdio.h>
#include <string.h>

// Function to perform a simple decryption using XOR
void desDecrypt(const char *ciphertext, const char *key, char *decryptedText) {
    for (int i = 0; i < 8; i++) {
        decryptedText[i] = ciphertext[i] ^ key[i];
    }
}

int main() {
    char key[8] = "KEY12345";  // 8-byte key
    char ciphertext[8] = {0x03, 0x0C, 0x00, 0x0F, 0x1C, 0x0F, 0x03, 0x06}; // Encrypted message
    char decryptedText[8];

    // Decrypt the ciphertext
    desDecrypt(ciphertext, key, decryptedText);

    // Print the decrypted text
    printf("Decrypted Text: %s\n", decryptedText);

    return 0;
}
```





## Output:
### Encryption:
![image](https://github.com/user-attachments/assets/f939487c-ca34-40a7-92fe-a1e44385f9f6)
### Decryption:
![image](https://github.com/user-attachments/assets/91f1d372-3048-45fb-ae89-bbe753b0516f)



## Result:
  The program is executed successfully

