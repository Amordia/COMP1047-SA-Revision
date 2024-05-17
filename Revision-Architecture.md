# Introduction & Computer Performance

## Von Neumann architecture

 Von Neumann architecture (also called  Princeton architecture) is still the state-of the-art computing architecture adopted. **Relationship between von Neumann Architecture and MlPS ISA**: MIPS ISA is an implementation of the von Neumann Architecture.
---

## Key Metrics of Computer Performance

### Relative Performance
- **Relationship between performance and execution time**:
  - Performance $\text{Performance}_X$ is defined as $\frac{1}{\text{Execution Time}_X}$
  
  - If Computer X is n times faster than Computer Y, the relative performance \( n \) can be expressed as:
    $$
    n = \frac{\text{Performance}_X}{\text{Performance}_Y} = \frac{\text{Execution Time}_Y}{\text{Execution Time}_X}
    $$
  
- 

### CPU Time
- **Calculation of CPU time**:
  - $$ \text{CPU Time} = \frac{\text{Number of CPU Clock Cycles}}{\text{Clock Rate}} $$
- **Methods to improve performance**:
  - Reduce the number of clock cycles
  - Increase the clock rate
  - However, these factors are limited by circuit design and cannot be altered arbitrarily.

### Instruction Performance
- **Clock Cycles per Instruction (CPI)**:
  - The average number of clock cycles required for executing an instruction.
  - $$ \text{CPU Clock Cycles} = \text{Instruction Count} \times \text{CPI} $$
- **Instruction count of a program**:
  - Determined by the program, compiler, etc.

### Classic CPU Performance Equation
- **Method to calculate CPU time**:
  - $$ \text{CPU Time} = \text{Instruction Count} \times \text{CPI} \times \text{Clock Period} $$

### CPI Example
- **Comparing the speed of two computers running the same program**:
  - Computer A: Clock Period = 250ps, CPI = 2.0
  - Computer B: Clock Period = 500ps, CPI = 1.2
  - CPU Time for Computer A = $C \times 2.0 \times 250\text{ps}$
  - CPU Time for Computer B = $C \times 1.2 \times 500\text{ps}$
  - Computer A is 1.2 times faster than Computer B.

### Detailed Analysis of CPI
- **Different instruction classes may require different numbers of cycles**:
  - Total number of clock cycles = $$ \sum (\text{CPI}_i \times \text{Instruction Count}_i) $$
- **Calculation of average CPI**:
  - Average CPI = $$ \frac{\sum (\text{CPI}_i \times \text{Instruction Count}_i)}{\text{Total Instruction Count}} $$

### Performance Summary
- **Basic components of performance**:
  - CPU execution time
  - Instruction count
  - Clock cycles per instruction (CPI)
  - Clock cycle time (period)

### Other Metrics

#### Power & Energy

- **Dynamic Power**: P = 0.5 * C * V^2 * f, where C is the effective capacitance, V is the voltage, and f is the frequency.
- **Static/Leakage Power**: Becomes significant in advanced process technologies and contributes to heat generation.
- **Dynamic Energy**: P * t, which relates to battery life and power consumption.

#### Bandwidth

- The amount of work or data processed over a period of time, often used in the context of networks or disk performance.

#### Reliability

- **Mean Time to Failure (MTTF)**: The average time before a system stops working, which is complex to calculate for complex systems.

---



---

# MIPS programming



---



---

# MIPS ISA

![image-20240513020716632](C:\Users\23650\AppData\Roaming\Typora\typora-user-images\image-20240513020716632.png)

One instruction is in 32 bits:

- Divide the instruction word into “fields”.

-  Each “field” tells computer the info about the **operands** and **operations**.

Details of Fields:

- opcode : partially specifies what instruction it is  (Note: ‘0’ for all R-Format instructions).
- funct : combined with opcode to specify the  instruction. E.g. add: op(0), funct(32); sub: op(0),  funct(34). 
- rs (Source Register): used to specify register  containing first operand rt (S-next Register): used to specify register  containing second operand.
- rd (Destination Register): used to specify register which will receive result of calculation.
- shamt (shift amount): contains the amount a  shift instruction will shift by. Set to zero in other  cases.

Below is a well-organized Markdown guide explaining the translation of J, R, and I format instructions into bytecode, focusing on the MIPS architecture. It includes the general approach, key points, and examples for each instruction format.

---

## MIPS Instruction Formats to Bytecode

### R-Format Instructions

**General Approach and Key Points:**

- **Opcode**: First 6 bits are fixed, identifying the operation type (e.g., arithmetic operations).
- **Source and Destination Registers**: Next fields specify the registers involved. Each register is identified by a 5-bit number.
- **Shamt (Shift Amount)**: 5 bits, used for shift operations.
- **Funct**: Last 6 bits define the specific operation within the group specified by the opcode.

**Example - `add` Instruction:**
Assuming we want to perform `add $t1, $t2, $t3` ($t1 = $t2 + $t3).

- **Opcode**: `000000` (standard for R-type arithmetic instructions)
- **Register Numbers**: `$t1 = 9 (01001), $t2 = 10 (01010), $t3 = 11 (01011)`
- **Shamt**: `00000` (no shift needed for add)
- **Funct**: `100000` (specific code for `add`)
- **Form the instruction**: `000000 01010 01011 01001 00000 100000`

---

### I-Format Instructions

**General Approach and Key Points:**
- **Opcode**: First 6 bits determine the type of the instruction (e.g., `beq`, `addi`).
- **Registers**: The next two 5-bit fields specify the source and the target registers.
- **Immediate**: The last 16 bits represent an immediate value or an offset for branch instructions.

**Example - `beq` Instruction:**
Suppose `beq $t1, $t2, label` and the label is 100 instructions ahead.

- **Opcode**: `000100` (for `beq`)
- **Register Numbers**: `$t1 = 9 (01001), $t2 = 10 (01010)`
- **Calculate Offset**: Assuming the current instruction is at address `0x1000` and `label` is at `0x1190`, offset = (0x1190 - 0x1004) / 4 = 62.
- **Immediate Field**: Binary representation of 62 = `00000000 00111110`
- **Form the instruction**: `000100 01001 01010 00000000 00111110`

#### I-Format Instructions: Immediate Field Calculation

**Context:**
In I-format instructions, the `immediate` field is used for branch offsets or as direct values in arithmetic operations. The field is 16 bits and can represent either signed or unsigned values.

**Calculation:**
For branch instructions (like `beq` and `bne`), the `immediate` field represents the offset from the current instruction to the target instruction, where the program should jump if the condition is true. This offset is calculated as:
$$
\text{Current PC Address} + 4 + (\text{Immediate}<<2) = \text{Target Address}
$$
The above can be written as:
$$
\text{Immediate} = \frac{\text{Target Address} - (\text{Current PC Address} + 4)}{4}
$$

- **Current PC Address**: This is the address of the instruction immediately following the branch instruction.
- **Target Address**: This is the address of the instruction to which control should transfer if the condition is met.
- **Division by 4**: This is because MIPS instructions are word-aligned (each instruction is 4 bytes).

**Example:**
If you have a `beq` instruction at address `0x1000` that should branch to an instruction at `0x1020` when the condition is true:
$$
\text{Immediate} = \frac{0x1020 - (0x1000 + 4)}{4} = \frac{0x1020 - 0x1004}{4} = 7
$$

---

###  J-Format Instructions

**General Approach and Key Points:**

- **Opcode**: First 6 bits represent the instruction type. For jump instructions like `j` and `jal`, specific opcodes are used (`000010` for `j` and `000011` for `jal`).
- **Jump Target Address (JTA)**: 26 bits derived from the target address. It's the address shifted right by 2 bits (divided by 4) to fit into the 26-bit field.

**Example - `j` Instruction:**
Let's say we want to jump to the address `0x00403000`.

- **Calculate the JTA**: 
  - Full address: `0x00403000`
  - Adjusted for the format: Shift the address right by 2 bits: `0x00403000 >> 2 = 0x00100c00`
  - JTA is the lower 26 bits of the result: `000100 000011 000000 000000`
- **Form the instruction**:
  - Opcode for `j`: `000010`
  - Complete instruction: `000010 000100 000011 000000 000000`

#### J-Format Instructions: Jump Target Field Calculation

**Context:**
In J-format instructions (like `j` and `jal`), the `jump target` field specifies the address to which the program should unconditionally jump. This field is 26 bits long.

**Calculation:**
The `jump target` field is calculated by taking the full 32-bit address, ignoring the lowest two bits (since instructions are word-aligned), and then using the next 26 bits from this result:
$$
\text{Jump Target} = \left(\frac{\text{Full Target Address}}{4}\right) \& \text{0x03FFFFFF}
$$

- **Full Target Address**: This is the absolute address to which the jump should occur.
- **Division by 4**: This adjusts for word alignment by removing the two least significant bits.
- **Bitwise AND with 0x03FFFFFF**: This ensures that only the lower 26 bits are used.

**Example:**
If the jump should occur to address `0x00403000`:
$$
\text{Jump Target} = \left(\frac{0x00403000}{4}\right) \& \text{0x03FFFFFF} = 0x00100C00
$$

---



---

