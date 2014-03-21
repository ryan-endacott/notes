# Types of function calls

## Call-by-value over program memory after JSR

Without pulling off the stack:
```
    JSR   SUB
    FCB   5

SUB TSX
    LDY   0,X  get return addres
    LDAA  0,Y  get data
    INY        adjust return address
    STY   0,X  update return address on stack
    RTS


```

## Call-by-reference in register (X/Y, not D)

```
      ORG   $B000
DATA  FCB   5

      ORG   $C000

      LDX   #DATA
      JSR   SUB

SUB   LDAA  0,X get data
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

SUB   PULY      get return address
      PULX      get data address
      LDAA  0,X get data
      PSHY      put return address back on stack

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

SUB   PULX      get return address
      LDY   0,X get data address
      LDAA  0,Y get data
      INX       * LDAB #2
      INX       adjust return address * ABX  X += 2
      PSHX      put return address back on stack
      RTS
```

## Call-by-reference with array and store array sum in result variable

in subroutine:
X: pointer to TABLE
Y: pointer to RESULT
B: data addition; return addr. adjust
```
        ORG   $B000
TABLE   FCB   1,2,3,$FF
RESULT  RMB   1

        ORG   $C000
        LDS   #$01FF
        JSR   SUB
        FDB   TABLE
        FDB   RESULT

SUB     TSX         get stack addr
        LDY   0,X   get return addr
        LDX   0,Y   get TABLE addr
        LDY   2,Y   get RESULT addr
        CLR   0,Y   clear RESULT
WHILE   LDAB  0,X   get table item in B register
        CMPB  #$FF
        BEQ   ENDWL exit if it is equal to sentinel
        ADDB  0,Y   add result to B
        STAB  0,Y   store back in result
        INX         next item in table
        BRA   WHILE
ENDWL   TSY         get stack addr
        LDX   0,Y   get return addr
        LDAB  #4
        ABX         add 4 to return address
        STX   0,Y   update return addr on stack
        RTS
```

