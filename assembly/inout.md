# Programmable In/Out Port Example

[C7--------Port C-_-----C0]
in in out out out out in in
00111100 = $3C

Code:
```

PORTC EQU   $1003 * loc of port C
DDRC  EQU   $1007 * Data direction register for C, 0 = input, 1 = output

      ORG   $C000

      CLR   PORTC (clear outputs)

      * set pins to be in/out as specified above
      LDAA  #$3C
      STAA  DDRC

      LDAA  PORTC (get bits 0,1,6,7)

      LDAA  #$FF
      STAA  PORTC  (send 1 to bits 2,3,4,5)

```



