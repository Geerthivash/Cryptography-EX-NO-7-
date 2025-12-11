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

int main() {
    char P[100], E[100], D[100];
    int K = 0xAA;          // Base key
    int K1 = K ^ 0x01;     // Subkey 1
    int K2 = K ^ 0x02;     // Subkey 2

    printf("Enter Plaintext: ");
    scanf("%[^\n]", P);

    int len = strlen(P);

    // --- Encryption ---
    for(int i=0; i<len; i++) {
        if(i % 2 == 0)    // even index
            E[i] = P[i] ^ K1;
        else              // odd index
            E[i] = P[i] ^ K2;
    }
    E[len] = '\0';

    // --- Decryption ---
    for(int i=0; i<len; i++) {
        if(i % 2 == 0)
            D[i] = E[i] ^ K1;
        else
            D[i] = E[i] ^ K2;
    }
    D[len] = '\0';

    printf("Plain:     %s\n", P);

    printf("Encrypted (decimal bytes): ");
    for(int i=0; i<len; i++)
        printf("%d ", (unsigned char)E[i]);
    printf("\n");

    printf("Decrypted: %s\n", D);

    return 0;
}

```


## Output:
<img width="641" height="531" alt="image" src="https://github.com/user-attachments/assets/13efd84c-8c41-4a6b-8497-57624e96a70b" />


## Result:
  The program is executed successfully

