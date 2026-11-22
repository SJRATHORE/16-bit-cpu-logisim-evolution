# Instruction set: assignment targets vs. verified implementation

**Important:** The items below come from the supplied final pre-release and boss-level assignment documents. Their presence here **does not establish that the corresponding microcode or datapath has passed tests**.

The specifications discuss: `ADD`, `SUBTRACT` (flag variant of ADD), `MULTIPLY`, `STORE`, `STORE OVERFLOW` (flag variant), `MEM SWAP`, `COMPARE`, `NOT`, `REG SWAP`, `BLOCK LOAD`, `BLOCK STORE`, `MAT MULT`, and `MOVE` variants (boss-level addendum). The final addendum lists 17 instructions; the boss-level addendum lists 19. These counts refer to different specification revisions.

The original course slide deck gives an early **16-bit instruction layout**: 1 flag bit, 5 opcode bits, 5 address-1 bits, 5 address-2 bits. Later slides and addenda discuss changes; the final decoder and flag behaviors must be confirmed from the chosen CPU circuit before listing exact opcode encodings.

## Verification table (to be completed)

| Instruction / family | Source of requirement | Verified? | Test evidence |
| --- | --- | --- | --- |
| Add / subtract | Final pre-release | Not yet tested | — |
| Multiply | Final pre-release | Not yet tested | — |
| Store / overflow store | Final pre-release | Not yet tested | — |
| Compare / NOT | Final pre-release | Not yet tested | — |
| Memory swap / register swap | Final pre-release | Not yet tested | — |
| Block Load / Block Store | Final pre-release | Not yet tested | — |
| 2×2 Matrix Multiply | Final pre-release | Not yet tested | — |
| MOVE flag variants | Boss-level addendum | Not yet tested | — |

Once the exact final CPU and ROM microprogram are identified, add a machine-code encoding table, cycle-by-cycle control-sequence explanation and verified example for each instruction.
