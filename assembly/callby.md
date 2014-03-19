# Types of function calls


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

