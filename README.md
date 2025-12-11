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

void main(){
    char P[] = "HI";  // 2-byte Plaintext Block
    int K = 0xAA;     // Initial Key
    int K1 = K ^ 0x01; // Subkey 1
    int K2 = K ^ 0x02; // Subkey 2
    char E[3], D[3];

    // Encryption (Simulated 2 Rounds)
    E[0] = P[0] ^ K1;
    E[1] = P[1] ^ K2;
    E[2] = '\0'; // Null terminator

    // Decryption (Simulated 2 Rounds)
    D[0] = E[0] ^ K1;
    D[1] = E[1] ^ K2;
    D[2] = '\0';

    printf("Plain:     %s\n", P);
    printf("Encrypted: %d %d\n", E[0], E[1]);
    printf("Decrypted: %s\n", D);
}
```


## Output:
<img width="641" height="531" alt="image" src="https://github.com/user-attachments/assets/13efd84c-8c41-4a6b-8497-57624e96a70b" />


## Result:
  The program is executed successfully

