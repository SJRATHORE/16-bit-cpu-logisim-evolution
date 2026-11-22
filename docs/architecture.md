# Architecture notes

## Observed structure

The Logisim project XML identifies 56 named circuits and has saved `main` as its initial circuit. The `main` schematic includes four RAM components, each set to 5-bit addresses and 16-bit data, eight labeled `Reg_1`–`Reg_8` general registers, MAR/MBR labels, an `Aloo` ALU instance, an instruction splitter, a ROM and two counters. Other CPU variants use different control-ROM data widths; for example `main` declares a 9-bit-address, 48-bit-data ROM while `Prize_Circuit_10_Final_BOSS` declares a 9-bit-address, 64-bit-data ROM.

The assignment asks for four RAM blocks, three 5-bit MARs, three 16-bit MBRs, eight 16-bit input registers, a 16-bit output register, an ALU, a ROM-based PCU, multiple 16-bit buses, and (in later versions) a bus terminal. These are requirements, not a validation report.

## Dataflow constraints in the boss-level addendum

- Data passes to the ALU via registers.
- Data passes to registers via MBRs.
- Memory addresses are routed via appropriate MARs.
- Data writes to RAM are routed via MBRs.
- Program counters control execution flow; hard-coded cycle sequencing is prohibited.

## Final design and documentation boundaries

- **Final submitted circuit confirmed by the developer:** `BOSS_VIVA_JUMP_3`. The saved `main` is an earlier default, not the final CPU.
- Review the final circuit wiring before publishing exact signal timing diagrams.
- Derive a final datapath diagram from that variant.
- Confirm bus contention protections, clocking, reset behavior and memory initialization.
- Explain ROM microinstruction bit fields and program-counter coordination.
- Show complete fetch-decode-execute control signals for at least one tested instruction.
