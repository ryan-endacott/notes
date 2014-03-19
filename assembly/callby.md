# Types of function calls

## Call-by-value over program memory after JSR

Without pulling off the stack:
```
  JSR SUB
  FCB 5

SUB TSX
    LDY 0,X get return addres
    LDAA 0,Y get data
    INY     adjust return address
    STY 0,X  update return address on stack
    RTS


```

## Call-by-reference in register (X/Y, not D)

```
      ORG $B000
DATA  FCB 5

      ORG $C000

      LDX #DATA
      JSR SUB

SUB   LDAA 0,X get data
      RTS

```

## Call-by-reference over the stack

```

      ORG $B000
DATA  FCB 5

      ORG $C000
      LDX #DATA
      PSHX
      JSR SUB

SUB   PULY get return address
      PULX  get data address
      LDAA  0,X get data
      PSHY  put return address back on stack

      RTS
```

## Call-by-reference in program memory after JSR

With pulling off the stack:
```
      ORG $B000
DATA  FCB 5

      ORG $C000
      JSR SUB
      FDB DATA

SUB   PULX get return address
      LDY 0,X get data address
      LDAA  0,Y get data
      INX  * LDAB #2
      INX   adjust return address * ABX  X += 2
      PSHX  put return address back on stack
      RTS
```


Without pulling off the stack:

