

How to add 2 N-byte numbers (N > 1) with little-endian

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
Pointer2 = &NUMB2[0];
CF(carry flag) = 0

Do {
  Pointer1->item +
  Pointer2->item + CF =
  Pointer1item
  Pointer1++;
  Pointer2++;
  Counter--;
} until (counter == 0)
```

Program section
```assembly
ORG $C000
    LDAB  #N
    LDX   #NUMB1
    LDY   #NUMB2
    CLC

DO    LDAA  0,X
      ADCA  0,Y * Note: carry flag must be preserved in whole loop
      STAA  0,X
      INX
      INY
      DECB
UNTIL BNE   DO

DONE  BRA   DONE
```


With big-endian, change:
```
LDX #NUMB1 -> LDX #NUMB1+N-1
LDY #NUMB2 -> LDY #NUMB1+N-1

INX -> DEX
INY -> DEY
```
And it works!


