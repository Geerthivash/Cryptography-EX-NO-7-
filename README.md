# EX-NO-7-Implement-DES-Encryption
```
GEERTHIVASH J.D. - 212223060067
```
## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```
#include <stdio.h>
#include <string.h>
unsigned char feistel(unsigned char half, unsigned char key) {
return half ^ key; // Just XOR for demonstration
}
void simple_DES_encrypt(char *plaintext, unsigned char key) {
unsigned char left = plaintext[0];
unsigned char right = plaintext[1];
printf("Initial L=%c, R=%c\n", left, right);
for (int round = 1; round <= 4; round++) {
unsigned char temp = right;
right = left ^ feistel(right, key + round); // F-function
left = temp;
printf("Round %d -> L=%c, R=%c\n", round, left, right);
}
plaintext[0] = left;
plaintext[1] = right;
}
void simple_DES_decrypt(char *ciphertext, unsigned char key) {
unsigned char left = ciphertext[0];
unsigned char right = ciphertext[1];
printf("Initial L=%c, R=%c\n", left, right
for (int round = 4; round >= 1; round--) {
unsigned char temp = left;
left = right ^ feistel(left, key + round);
right = temp;
printf("Round %d -> L=%c, R=%c\n", round, left, right);
}
ciphertext[0] = left;
ciphertext[1] = right;
}
int main() {
char text[3] = "HI"; // 2 chars = 16 bits (like one DES block simplified)
unsigned char key = 0x0F;
printf("Plaintext: %s\n", text);
simple_DES_encrypt(text, key);
printf("Ciphertext: %c%c\n", text[0], text[1]);
simple_DES_decrypt(text, key);
printf("Decrypted: %c%c\n", text[0], text[1]);
return 0;
}
```


## Output:
<img width="641" height="531" alt="image" src="https://github.com/user-attachments/assets/13efd84c-8c41-4a6b-8497-57624e96a70b" />


## Result:
  The program is executed successfully

