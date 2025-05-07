# EX-NO-9-RSA-Algorithm

## AIM:
To Implement RSA Encryption Algorithm in Cryptography

## Algorithm:


Step 1: Design of RSA Algorithm  
The RSA algorithm is based on the mathematical difficulty of factoring the product of two large prime numbers. It involves generating a public and private key pair, where the public key is used for encryption, and the private key is used for decryption.

Step 2: Implementation in Python or C 
This algorithm can be implemented in languages like Python or C by performing large integer calculations for key generation, encryption, and decryption, utilizing libraries for modular arithmetic if necessary.

Step 3: Algorithm Description  
1. Key Generation:
   - Select two large prime numbers \( p \) and \( q \).
   - Calculate \( n = p \times q \), which will be used as the modulus.
   - Compute the totient \( \phi(n) = (p - 1)(q - 1) \).
   - Choose a public exponent \( e \) such that \( e \) is coprime with \( \phi(n) \).
   - Compute the private key \( d \), which is the modular inverse of \( e \) mod \( \phi(n) \).

2. Encryption:
   - Convert the plaintext message \( M \) into a numerical form \( m \) (such that \( 0 \le m < n \)).
   - Compute the ciphertext \( c \) using the formula: \( c = m^e \mod n \).

3. Decryption:
   - Use the private key \( d \) to recover \( m \) from \( c \) using: \( m = c^d \mod n \).
   - Convert \( m \) back into the original message \( M \).

Step 4: Mathematical Representation  
- Encryption: \( E(m) = m^e \mod n \)
- Decryption: \( D(c) = c^d \mod n \)

Step 5: **Security Foundation  
The security of RSA relies on the difficulty of factoring large numbers; thus, choosing sufficiently large prime numbers for \( p \) and \( q \) is crucial for security.

## Program:
```
#include <stdio.h>  
#include <math.h>  
long long gcd(long long a, long long b) {  
while (b != 0) {         
long long temp = b;         
b = a % b;        
temp;  
}  
return a;  
}  
 a = 
long long modInverse(long long a, long long m) {     
a = a % m;     for (long long x = 1; x < m; x++) {         
if ((a * x) % m == 1) {             
}  
}  
return 1;  
}  
return x;  
long long power(long long base, long long exp, long long mod) {     
long long result = 1;     base = base % mod;     while (exp > 0) {         
if (exp % 2 == 1) {            
}  
exp = exp >> 1;         
(base * base) % mod;  
}  
return result;  
 result = (result * base) % mod;  
base = 
}  
int isPrime(long long n) {     if (n <= 1) 
return 0;     for (long long i = 2; i <= 
sqrt(n); i++) {        
0;  
}  
}  
return 1;  
int main() {    
 if (n % i == 0) return 
 long long p, q, n, phi, e, d, message, encryptedMessage, 
decryptedMessage;  
// Choose two prime numbers     printf("Enter prime 
number p: ");     scanf("%lld", &p);     while (!isPrime(p)) {         
printf("p is not a prime number. Enter a prime number: ");         
scanf("%lld", &p);  
}  
printf("Enter prime number q: ");     scanf("%lld", &q);     
while (!isPrime(q)) {        
a prime number: ");         
}  
// Calculate n = p * q     
n = p * q;  
 printf("q is not a prime number. Enter 
scanf("%lld", &q);  
// Calculate phi(n) = (p-1)*(q-1)     
phi = (p - 1) * (q - 1);  
// Choose e such that 1 < e < phi(n) and gcd(e, phi(n)) = 1     printf("Enter public 
key exponent e (1 < e < %lld and gcd(e, %lld) = 1): ", phi, phi);     scanf("%lld", &e);     
while (gcd(e, phi) != 1) {        
scanf("%lld", &e);  
}  
 printf("Invalid e. Enter a valid public key exponent: ");         
// Calculate the private key d such that (d * e) % phi = 1  
d = modInverse(e, phi);  
// Enter the message  
printf("Enter the message to encrypt (as an integer): ");     
scanf("%lld", &message);  
// Encrypt the message     encryptedMessage = 
power(message, e, n);     printf("Encrypted message: 
%lld\n", encryptedMessage);  
// Decrypt the message     decryptedMessage = 
power(encryptedMessage, d, n);     printf("Decrypted 
message: %lld\n", decryptedMessage);  
return 0;  
}  
```



## Output:

![image](https://github.com/user-attachments/assets/34d5867b-befe-4037-a9df-71efdf081030)


## Result:
 The program is executed successfully.
