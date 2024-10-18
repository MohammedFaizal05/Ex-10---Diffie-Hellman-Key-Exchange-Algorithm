# EX-10 To-Implement-Diffie-Hellman-Key-Exchange-Algorithm-in-C-program


## AIM:
To Implement Diffie Hellman Key Exchange Algorithm in C program.


## Program
```
#include <stdio.h>
#include <math.h>


long long mod_pow(long long base, long long exp, long long mod) {
    long long result = 1;
    base = base % mod;
    while (exp > 0) {
        if (exp % 2 == 1)
            result = (result * base) % mod;
        exp = exp >> 1;
        base = (base * base) % mod;
    }
    return result;
}

int main() {
    long long p, g; 

    printf("Enter a large prime number (p): ");
    scanf("%lld", &p);
    printf("Enter a primitive root of %lld (g): ", p);
    scanf("%lld", &g);

    long long a, b; 
    printf("Enter Alice's private key (a): ");
    scanf("%lld", &a);
    printf("Enter Bob's private key (b): ");
    scanf("%lld", &b);

    
    long long A = mod_pow(g, a, p); 
    long long B = mod_pow(g, b, p); 

    printf("Alice sends her public key (A) to Bob: %lld\n", A);
    printf("Bob sends his public key (B) to Alice: %lld\n", B);

    long long shared_secret_Alice = mod_pow(B, a, p); 
    long long shared_secret_Bob = mod_pow(A, b, p);   

    printf("Shared secret computed by Alice: %lld\n", shared_secret_Alice);
    printf("Shared secret computed by Bob: %lld\n", shared_secret_Bob);

    if (shared_secret_Alice == shared_secret_Bob) {
        printf("Key exchange successful! Shared secret: %lld\n", shared_secret_Alice);
    } else {
        printf("Key exchange failed! Shared secrets do not match.\n");
    }

    return 0;
}

```
## Output
![Screenshot 2024-10-18 142820](https://github.com/user-attachments/assets/bec65fb2-e060-46c2-97f9-b078d118283b)


## Result:
Hence,Implement Diffie Hellman Key Exchange Algorithm in C program executed successfully!!!
