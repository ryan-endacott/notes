
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
  (ADD Y, R, R) // Sets R to y + r
  (SUB R, X, Y) // Sets Y to R - X
  (JMP CASEEND)

LABEL DEFAULT
  (ADD X, 1, X) // x := x + 1

LABEL CASEEND

RETURN
```


Problem for giving intermediate representation for fibonacci

```
LABEL FIB_L
SET UP ACTIVATION FIB_L

(GT X, 2, R)
(JMP0, R, ELSE_LABEL)
  (SUB X, 1, R)
  PARAM R
  CALL FIB_L, 1 // passing one param, that is what the 1 means
  (MOV R, RV) // store return value in R so it isn't lost
  (SUB X, 2, R1) // make new param
  PARAM R1
  CALL FIB_L, 1
  (ADD RV, R, RV)

LABEL ELSE_LABEL
  (MOV RV, 1)
RETURN

```


