# chromite-bug-bounty
Part of the course Chromite Bug Bounty special topic

Week-1:
i)Ratified extensions of unprivileged spec(v2.1):
M,A,F,D,Q,C,Zicsr,Zifencei

ii)4 unratified extensions of unprivileged spec:
B,J,T,P

iii)Rason for immediate encoding being jumbled:
Decoding of the immediate becomes easier.A multiplexer maps the output immediate to the input bit it comes from.By jumbling the immediates, the mux has few options to select from to decode the data.
Ex: Immediate bit 0 can only come from instruction bit 7, 20 or constant zero.

iv)Within the 32-bit instruction format, how many more instructions can be added?
As 5 bits are used to depict the opcode(bit 1 & 0 are 11 for RV32),a total of 32 instructions can be addressed.
Of these, 4 major opcodes are reserved for custom extensions(RV128 can be used too).
2 opcodes reserved for RV64(OP-IMM-32 &  OP-32) can be used for extensions.
If floating point operations are not needed, 7 major opcodes(LOAD-FP,STORE-FP,MADD,MSUB,NMSUB,NMADD,OP-FP) can be reused for non standard extensions.
If atomic extension is not required AMO can be reused.
If only 32 bit instructions are considered, then bits 2 to 4 can be 111, giving an additional 4 major opcodes.
3 major opcodes are reserved and cannot be used.
Thus, a total of 12 major opcodes can be added, excluding the 4 custom opcodes.


