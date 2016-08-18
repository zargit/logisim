# logisim
1) The following mips program is loaded in the instruction memory:
	
	addi $t0, $zero, 1
	addi $t2, $zero, 100
	sub $t1, $t1, $t1
	loop:
	add $t1, $t1, $t0
	sw $t1, x
	bne $t1, $t2, loop
	lw $t3, 0
	add $t3, $t3, $t3
	sw $t3, 1

In Hexadecimal:
	20080001 //addi
	200a0064 //addi
	01294822 //sub
	01284820 //add
	ac290000 //store
	152afff4 //bne
	8c2b0000 //load
	016b5820 //add
	ac2b0001 //store

After the execution ends the first two memory block in the RAM is 64 and C8.

2) CPU is the overall design, it contains a 32 bit ALU, Register File with 32 registers, Main Control, ALU Control and Next PC.

3) It executes all the basic R-Type commands (add, sub etc), I-Type commands (addi, beq, bne), J-Type command (jump).

4) Logisim support 32 data bit but not 32 address bit, only 24 address bit. For that reason all the address bit has been truncated to 24 bit address for ROM and RAM.

5) Increasing the tick frequency in simulator option will make it run quicker and will produce the output faster. But to follow how its working we should reduce the tick frequency.

6) The less bit related operations (slt, slti etc) is still not supported.
