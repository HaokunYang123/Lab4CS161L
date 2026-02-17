Section 1:
the hardest part for this lab is the wiring because I did not use the tunnels and I just wired everything on the surface so its very hard to see where all the wires went. I just kept on trying and eventually I fixed all the wiring issue. And the Digital tells you where is wrong by the big red circle.

Section 2:
and $t0 $t1 $t2 => 000000 01001 01010 01000 00000 100100
addi $t3 $t4 123 => 00100 01100 01011 0000000001111011
lw $t5, 135($t1) => 10011 01001 01101 0000000010000111
sw $t3, 136($t1) => 101011 01001 01011 0000000010001000
beq $t3, $zero, -10 => 000100 01011 00000 1111111111110110

Tracing part:
lw $v0 31($zero)    PC = 0 opcode = 0x23 dst_addr = 2 dst_data = 0x00000056 
add $v1 $v0 $v0     PC = 4 opcode = 0x00 dst_addr = 3 dst_data = 0x000000AC 
sw $v1 132($zero)   PC = 8 opcode = 0x2B dst_addr = 3 dst_data = 0x00000084
sub $a0 $v1 $v0.    PC = 12 opcode = 0x00 dst_addr = 4 dst_data = 0x00000056
addi $a1 $v1 12.    PC = 16 opcode = 0x08 dst_addr = 5 dst_data = 0x000000B8
and $a2 $a1 $v1.    PC = 20 opcode = 0x00 dst_addr = 6 dst_data = 0x000000A8
or $a3 $a2 $v0.     PC = 24 opcode = 0x00 dst_addr = 7 dst_data = 0x000000FE
nor $t0 $a2 $v0.    PC = 28 opcode = 0x00 dst_addr = 8 dst_data = 0xFFFFFF01
slt $a2 $a1 $a0.    PC = 32 opcode = 0x00 dst_addr = 6 dst_data = 0x00000000
beq $a2 $zero -8.   PC = 36 opcode = 0x04 dst_addr = 31 (I am not sure why its 31 on Digital, but It should be 6) dst_data = 0x000000B8
lw $t0 132($zero).  PC = 40 opcode = 0x23 dst_addr = 8 dst_data = 0x000000AC
