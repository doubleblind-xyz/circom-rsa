# circom-rsa

This package is a work in progress; docs will be updated soon.

Examples:
- testing fp.circom https://zkrepl.dev/?gist=171ce146cb764e5009ec4e81a64b7c52 (a = 5, b = 5, p = 17; out = a * b mod p = 8)
- testing rsa.circom https://zkrepl.dev/?gist=c7aebe4d2ee17e9706e53a87b1fb2573 (todo -- i forgot how to do secpk stuff)

```
component main { public [ a, b, p ] } = FpMul(10, 2); // toy example -- each bignum is 2 10-bit words

/* INPUT = {
    "a": ["5", "0"],
    "b": ["5", "0"],
    "p": ["17", "0"]
} */
```

# technical notes
- this circuit is intended to be used with RSASSA-PKCS1-v1_5 (see https://en.wikipedia.org/wiki/PKCS_1 and https://datatracker.ietf.org/doc/html/rfc8017#section-9.2). This is the signature scheme used by most applications that use RSA as their underlying cryptosystem
- circuit diagram: 
![circom-rsa](https://user-images.githubusercontent.com/1988030/217059345-9ed95a1c-c766-455f-9032-c846f1759030.png)


# todos (before publish)
- fix the array lengths in ab_proper / getProperRepresentation? length mismatch + hardcoded
- example for testing rsa.circom
- example code for installing & import of circom-rsa circuits (note peer dependency)
- double check code copying (copying bigint & bigint_func from 0xPARC/circom-ecdsa)
- double check GPL license (depending on circom ==> gpl-3.0?)

## Credits
Contributors: @ecnerwala, @stevenhao
Thanks: @iden3, @0xPARC
