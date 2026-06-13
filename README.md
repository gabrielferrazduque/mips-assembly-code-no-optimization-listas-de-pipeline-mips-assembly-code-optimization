# mips-assembly-code-no-optimization-listas-de-pipeline-mips-assembly-code-optimization
Mips-Assembly listas de pipeline
Loop Optimizations 
# Original
loop:
    lw   $t0, 0($s0)
    add  $t0, $t0, $s1
    sw   $t0, 0($s0)
    addi $s0, $s0, 4
    addi $t1, $t1, -1
    bne  $t1, $zero, loop

# Unrolled x2 
loop:
    lw   $t0, 0($s0)
    lw   $t2, 4($s0)
    add  $t0, $t0, $s1
    add  $t2, $t2, $s1
    sw   $t0, 0($s0)
    sw   $t2, 4($s0)
    addi $s0, $s0, 8
    addi $t1, $t1, -2
    bne  $t1, $zero, loop
