
# Exam 2

Sample problem 3:
Write as english, picture of tree, or pseudocode.
Every statement has type OK or type NOT OK.  OK if it type checks.
Case statement has type OK iff the following are true:
1. Exp must have type integer
2. Numi must be numeral
3. Each statement list must have type OK
4. Statement list default must have type OK



Sample problem for giving intermediate representations with case statement.


```
LABEL MAIN - LABEL // no activation record for main, just put in static memory

LABEL L0
(ISEQ X, 0, R)
(JMP0 R, L1) // jump to label 1 if R is 0, else continue

  (MOV Y, 0) // y:= 0
  (JMP CASEEND)

LABEL L1
(ISEQ X, 1, R) // Sets R to 1 if X == 1
(JMP0 R, DEFAULT) // jump to label default if R is 0

  (MULT Y, 8, R) // Sets R to y * 8
  (ADDI Y, R, R) // Sets R to y + r
  (SUBI R, X, Y) // Sets Y to R - X
  (JMP CASEEND)

LABEL DEFAULT
  (ADDI X, 1, X) // x := x + 1

LABEL CASEEND

RETURN
```


Problem for giving intermediate representation for fibonacci

```
LABEL FIB_L
SET UP ACTIVATION FIB_L containing stuff below on stack:
- Value of R1 (temporaries must be on the memory)
- Value of R
- old frame pointer (stack pointer points here)
- old stack pointer
- return label (address)
- value of x (frame pointer points here)
6*4 = 24 bytes for each function call.


(GT X, 2, R)
(JMP0, R, ELSE_LABEL)
  (SUBI X, 1, R)
  PARAM R
  CALL FIB_L, 1 // passing one param, that is what the 1 means
  (MOV R, RV) // store return value in R so it isn't lost
  (SUBI X, 2, R1) // make new param
  PARAM R1
  CALL FIB_L, 1
  (ADDI RV, R, RV)

LABEL ELSE_LABEL
  (MOV RV, 1)
RETURN


// Main to call fib
LABEL MAIN_LABEL
PARAM 4
CALL FIB_L, 1
(MOV Y, RV) y := return value
RETURN
```

Activation record is dynamic.  So is heap, but we will not be asked about it.
Stack and heap are dynamic.  Activation record is put on stack.

Static memory for fib:
- No global variables
- Y is in static memory


