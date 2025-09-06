
# Chapter 2 Exercise

**Name:** Kaniz Fatema  
**ID:** 20245103154

---

### 2.4 [5] <§§2.2, 2.3>

For the MIPS assembly instructions below, what is the corresponding C statement?

Assume:
- Variables `f`, `g`, `h`, `i`, and `j` are assigned to registers `$s0`, `$s1`, `$s2`, `$s3`, and `$s4`, respectively.
- The base addresses of the arrays `A` and `B` are in registers `$s6` and `$s7`, respectively.

```mips
sll $t0, $s0, 2        # $t0 = f * 4
add $t0, $s6, $t0      # $t0 = &A[f]
sll $t1, $s1, 2        # $t1 = g * 4
add $t1, $s7, $t1      # $t1 = &B[g]
lw  $s0, 0($t0)        # f = A[f]
addi $t2, $s0, 4
lw  $t0, 0($t2)
add $t0, $t0, $s0
sw  $t0, 0($t1)
```

>[!Note] This `2.6` Table is used for the question below

### 2.6
The table below shows 32-bit values of an array stored in memory.

| Address | Data |
|--------:|-----:|
| 24      | 2    |
| 38      | 4    |
| 32      | 3    |
| 36      | 6    |
| 40      | 1    |

### 2.9 [5] <§§2.2, 2.3>

Translate the following C code to MIPS.  
Assume that the variables `f`, `g`, `h`, `i`, and `j` are assigned to registers `$s0`, `$s1`, `$s2`, `$s3`, and `$s4`, respectively.  
Assume that the base addresses of the arrays `A` and `B` are in registers `$s6` and `$s7`, respectively.  
Assume that the elements of the arrays A and B are 4-byte words.

```c
B[8] = A[i] + A[j];
```
### 2.10 [5] <§§2.2, 2.3>

Translate the following MIPS code to C.
Assume that the variables `f`, `g`, `h`, `i`, and `j` are assigned to registers `$s0`, `$s1`, `$s2`, `$s3`, and `$s4`, respectively.
Assume that the base address of the arrays  A` and `B` are in registers `$s6` and `$s7`, respectively.

```mips
addi $t0, $s6, 4
add  $t1, $s6, $s0
sw   $t1, 0($t0)
lw   $t0, 0($t0)
add  $s0, $t1, $t0
```

### **2.19.1** [5] <§2.6>

For the register values shown above, what is the value of `$t2` for the following sequence of instructions?

```mips
sll $t2, $t0, 44
or  $t2, $t2, $t1
```
### 2.19.2 [5] <§2.6>

For the register values shown above, what is the value of `$t2` for the following sequence of instructions?

```mips
sll  $t2, $t0, 4
andi $t2, $t2, -1
```
### 2.19.3 [5] <§2.6>

For the register values shown above, what is the value of `$t2` for the following sequence of instructions?

```mips
srl  $t2, $t0, 3
andi $t2, $t2, 0xFFEF
```

### 2.23 [5] <§2.7>

Assume `$t0` holds the value `0x00101000`.  
What is the value of `$t2` after the following instructions?

```mips
    slt   $t2, $0, $t0
    bne   $t2, $0, ELSE
    j     DONE

ELSE: 
    addi  $t2, $t2, 2
DONE:
```
### **2.26**  Consider the following MIPS loop:
```mips
LOOP:  slt   $t2, $0, $t1
       beq   $t2, $0, DONE
       subi  $t1, $t1, 1
       addi  $s2, $s2, 2
       j     LOOP
DONE:
```
### **2.26.1** [5] <§2.7>
Assume that the register `$t1` is initialized to the `value 10`.
What is the value in register `$s2`, assuming `$s2` is initially zero?

### 2.26.2 [5] <§2.7>
For the loop above, write the equivalent C code routine.
Assume that the registers `$s1`, `$s2`, `$t1`, and `$t2` are C-level integers `A`, `B`, `i`, and `temp`, respectively.

### 2.26.3 [5] <§2.7> 
For the loops written in MIPS assembly above, assume that the register `$t1` is initialized to the `value N`. How many MIPS instructions are executed?

### **2.27** [5] <§2.7>
Translate the following C code to MIPS assembly code. Use a minimum number of instructions. Assume that the values of `a`, `b`, `i`, and `j` are in registers `$s0`, `$s1`, `$t0`, and `$t1`, respectively. Also, assume that register `$s2` holds the base address of the `array D`.

```c
for (i = 0; i < a; i++)
    for (j = 0; j < b; j++)
        D[4 * j] = i + j;
```
## 2.29 [5] <§2.7> 

Translate the following loop into C. Assume that the C-level integer i is held in register `$t1`, `$s2` holds the C-level integer called result, and `$s0` holds the base address of the integer MemArray.

```mips
add $t1, $0, $0      
LOOP: 
    lw   $s1, 0($s0) 
    add  $s2, $s2, $s1  
    addi $s0, $s0, 4    
    addi $t1, $t1, 1   
    slti $t2, $t1, 100  
    bne  $t2, $0, LOOP 
```
## 2.31 [5] <§2.8> 
Implement the following C code in MIPS assembly. What is the total number of MIPS instructions needed to execute the function?

```c
int fib(int n) {
    if (n == 0)
        return 0;
    else if (n == 1)
        return 1;
    else
        return fib(n - 1) + fib(n - 2);
}
```