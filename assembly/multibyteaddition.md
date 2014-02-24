

How to add 2 N-byte numbers (N > 1)

NUMB1 + NUMB2 -> NUMB1

Addition: register A
Counter: Register B
Pointer 1: X-register
Pointer 2: Y-register

```
*Data section
  ORG $B000
NUMB1 FCB $F0, $10, 4, 5 (LSB...MSB)
```

psuedocode:
```
Counter = N;
Pointer1 = &NUMB1[0];



