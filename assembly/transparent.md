# Transparent Subroutine Execution


Example:  Call-by-value in memory; subroutine uses A, X, CC
```
* main program
      JSR   SUB


* subroutine
SUB   PSHX
      PSHA
      TPA   *(Condition flags to A)
      PSHA

      * load the parameter
      TSX   * we cannot pull off the stack because we're using it
      LDX   4,X  * load the return address into X
      LDAA  0,X

      * do subroutine work here

      * fix the return address in stack memory, taking care of high byte
      TSX
IF    INC   5,X
      BNE   ENDIF
THEN  INC   4,X
ENDIF

      * put stuff back in registers
      PULA
      TAP
      PULA
      PULX
      RTS

```

