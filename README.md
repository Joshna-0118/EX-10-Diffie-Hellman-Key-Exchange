# EX-10-Diffie-Hellman-Key-Exchange
Implementation of the Diffie-Hellman Key Exchange Algorithm in C to establish a shared secret key between two parties using public and private keys.

## Name: Joshna.M
## Reference Number: 212225230118

# AIM:
To Implement Diffie Hellman Key Exchange Algorithm.

# Algorithm:
    1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

    2. Initialization: Agree on a large prime number ( p ) and a primitive root ( g ) modulo ( p ) (both are public values).

    3. Key Exchange Process:
        Each party selects a private key and calculates their public key using the formula ( g^{\text{private key}} \mod p ).
        Each party then shares their public key with the other.

    4. Secret Key Computation:
        Each party computes the shared secret key using the received public key and their own private key.

    5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

# Program:
```

#include <stdio.h>

int main() {
    int p, g, a, b, A, B, key1, key2;

    printf("Enter prime number (p): ");
    scanf("%d", &p);

    printf("Enter primitive root (g): ");
    scanf("%d", &g);

    printf("Enter Joshna's private key: ");
    scanf("%d", &a);

    printf("Enter John's private key: ");
    scanf("%d", &b);

    
    A = 1;
    B = 1;

    for (int i = 0; i < a; i++)
        A = (A * g) % p;

    for (int i = 0; i < b; i++)
        B = (B * g) % p;

    
    key1 = 1;
    key2 = 1;

    for (int i = 0; i < a; i++)
        key1 = (key1 * B) % p;

    for (int i = 0; i < b; i++)
        key2 = (key2 * A) % p;

    printf("\nJoshna's Public Key: %d", A);
    printf("\nJohn's Public Key: %d", B);
    printf("\nJoshna's Shared Key: %d", key1);
    printf("\nJohn's Shared Key: %d\n", key2);

    if (key1 == key2)
        printf("Shared Secret Key Established Successfully!\n");

    return 0;
}
```

# Output:

<img width="874" height="322" alt="image" src="https://github.com/user-attachments/assets/1d878c3d-ae53-48bb-a1c2-798f1547495e" />

# Result:
The Diffie-Hellman Key Exchange Algorithm was successfully implemented in C. Both Alice and Bob generated their public keys and calculated the same shared secret key using their respective private keys.
