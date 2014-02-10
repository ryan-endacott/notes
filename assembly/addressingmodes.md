# Addressing mode

## 1. Extended Addressing mode
EA = 16-bit effective address given in instruction

`ADDA $C210` -> `$BB, $C2, $10` -> `EA = $CS10`
Address range: whole memory

## 2. Direct Addressing Mode
`EA = 16-bit address`
`MSB = $00`
`LSB = address given`

`ADDA $C2` -> `$9B, $C2` -> `EA = $00C2`

Address range: Page 0 (`$0000 - $00FF`)
Advantages:
- Faster fetching of instructions (only 2 bytes instead of 3)
- Smaller program size (more efficient when only have 64K RAM)

## 3. Inherent Addressing Mode
No EA to be generated; data in processor, not in memory; or data not needed

`ABA` -> `$1B: (A) + (B) -> A`
Adds registers `A` and `B` and puts result in `A`.
Address range: N/A

## 4. Immediate Addressing Mode
No EA to be generated;
Pound sign means immediate addressing mode.

`ADDA #$C2` -> `$8B, $C2` -> `(A) + $C2 -> A`
Actually add the value `$C2` to `A`.

Note:  You are limited with `ADDA` to 1-byte constants because the `A` register is 1 byte.  The length of your constant is limited by the register.  The `D` register is 2 bytes, so you could use a larger constant.

Address range: N/A
BE CAREFUL:  ADDA #$C2 != ADDA $C2
The first adds the actual value $C2, the second adds the value in memory at $00C2
Immediate vs direct.
(A) + $C2 -> (A) vs. (A) + ($00C2) -> (A)
Parentheses denote using the value at a memory location.

## 5. Indexed Addressing Mode
Uses index registers `X` or `Y` as a base address instruction that provides a 1-byte unsigned offset.

EA = `(X) + offset`

`ADDA $C2, X` -> `$AB, $C2`
Address range: (X) to (X) + $FF

Example:
X contains $C200
And we execute `ADDA $C2, X`
`EA = (X) + $C2 = $C200 + $C2 = $C2C2`
So we add `(A) + ($C2C2) -> (A)`

Important: `ADDA $C2,X != ADDA $C2, X`
The space matters!

So those are the five addressing modes our microcontroller provides to get access to data items.  Pentium doesn't have direct addressing mode because it's already fast so nobody needs it for extra speed.

## 6. Relative Addressing Mode
Only used by branch instructions.
Branching: change program flow; jump to different sectionj;w

How? Change contents of Program Counter
branch instruction: opcode + 1-byte signed (2's comp) offset
`BRA 8` -> `$20, $08` -> `(PC) + 8 -> (PC)`
So jump 8 bytes down with program counter.

branch to itself (infinite loop):
`LOOP BRA LOOP`



