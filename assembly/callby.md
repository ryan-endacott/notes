# Types of function calls



# Call-by-value over program memory
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

# Call-by-reference in register (X/Y, not D)

```
      ORG $B000
DATA  FCB 5

      ORG $C000

      LDX #DATA
      JSR SUB

SUB   LDAA 0,X get data
      RTS

```


# Call-by-reference over the stack

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





