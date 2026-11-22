# Testing and reproducibility

## Historical assessment results

The developer reports these outcomes from the original project work:

| Program set | Outcome reported by author | Reproduced while preparing this GitHub archive? |
| --- | --- | --- |
| Practice scripts | Executed successfully | No |
| TA-viva scripts | Executed successfully | No |
| Boss-viva challenge | Had deliberately introduced errors requiring manual debugging; after correction it ran partially | No |

This table preserves the author's account without claiming a new independent verification of the circuit or a complete boss-viva pass.

## Understanding the memory images

**Instruction RAM** stores executable machine-code instructions; **RAM A and RAM B** store test data; the **control ROM** holds the controller's control words. These are different memories with different purposes.

| File | Intended location |
| --- | --- |
| `tests/memory-images/Practice_Script_Inst_RAM` | Instruction RAM (practice) |
| `tests/memory-images/Practice_Script_RAM_A` | RAM A (practice) |
| `tests/memory-images/Practice_Script_RAM_B` | RAM B (practice) |
| `tests/memory-images/TA_Viva_Inst_RAM` | Instruction RAM (TA viva) |
| `tests/memory-images/TA_Viva_RAM_A` | RAM A (TA viva) |
| `tests/memory-images/TA_Viva_RAM_B` | RAM B (TA viva) |
| `tests/memory-images/Boss_Viva_Script.txt` | Instruction RAM (boss challenge; original as supplied) |
| `src/rom/ROM_CONTENTS.hex` | CPU controller's control ROM; **not** Instruction RAM |

The supplied files use Logisim's `v3.0 hex words addressed` format. Do not overwrite the ROM contents with an Instruction RAM image. Store a backup of the `.circ` project before initializing memories.

## How to reproduce a run

1. Launch Logisim Evolution and open `src/16_Bit.circ`.
2. Choose **`BOSS_VIVA_JUMP_3`** in the circuit explorer (not the original saved `main`).
3. Confirm the controller ROM is initialized correctly; if required, load `src/rom/ROM_CONTENTS.hex` into the correct ROM block using its memory editor.
4. For a practice or TA run, load the matching trio of instruction and RAM A/B files into their respective memory blocks. For the boss challenge, use the appropriate debugged Instruction RAM script rather than assuming the supplied challenge is immediately runnable.
5. Reset the simulation using the circuit's intended procedure, and advance the clock using Logisim's simulation tools.
6. Inspect relevant registers and memory values; compare against expected outputs and capture screenshots when testing.

The exact clock/reset workflow and cycle counts depend on the circuit and should be verified in the simulator. This archive does not include an independently generated passing test log.
