# Assembly Language Paper 2 Solved By Anony_Khan:

---

## **Question 1:**


### (a) **Conditional Jump vs. Unconditional Jump in Assembly Language:**
   - **Conditional Jump:** This type of jump instruction transfers control to a different part of the program based on a certain condition. For example, a conditional jump might be executed only if a specific flag is set or cleared.
   - **Unconditional Jump:** This type of jump instruction transfers control to a different part of the program without any condition. It is executed regardless of the state of flags or any other conditions.

### (b) **Hexadecimal vs. Duodecimal Number System:**
   - **Hexadecimal (Base-16):** Uses 16 symbols (0-9 and A-F) to represent values. Convenient in computing because it aligns well with binary representation.
   - **Duodecimal (Base-12):** Uses 12 symbols (0-9 and A-B) to represent values. Historically proposed for its divisibility properties, but not as commonly used as hexadecimal.

### (c) **CMP Instruction in Assembly Language:**
   - The CMP (Compare) instruction is used to compare two operands in assembly language without actually modifying the operands. It affects the flags in the processor's status register based on the comparison.
   - Example:
     ```assembly
     MOV AX, 5    ; Load value 5 into AX register
     CMP AX, 7    ; Compare AX with 7
     ```
     In this example, the CMP instruction sets flags based on the comparison of AX and 7, and subsequent conditional jumps can be used to alter the program flow.

### (d) **Block Diagram of CISC Computer Architecture:**
   - A Complex Instruction Set Computer (CISC) architecture typically includes multiple instructions per program line,
     addressing modes, and a variety of instruction formats. The block diagram would include components like Control Unit, Memory
     Unit, ALU, Register File, and various specialized functional units. It might also include microcode for complex instructions.
    ![image](https://github.com/shaheeralics/BS-CS-3rd-A/assets/150110556/4117e2e1-2291-4d16-a055-57b2b144e1ca)

  
### (e) **Data Representation Formats in x86 Microprocessors:**
   - **Byte (8 bits):** Basic unit of data.
   - **Word (16 bits):** Two bytes.
   - **Doubleword (32 bits):** Four bytes.
   - **Quadword (64 bits):** Eight bytes.
   - **Single Precision (32 bits):** Used for floating-point arithmetic (float).
   - **Double Precision (64 bits):** Used for floating-point arithmetic (double).
   - **Extended Precision (80 bits):** Used for more precise floating-point arithmetic (long double).
   - **MMX, SSE, AVX Registers:** Specialized registers for multimedia and vector operations.

These formats allow the x86 architecture to handle various data types and operations efficiently.


---

## **Questionn 2:**

(a) **Steps Involved When 8086 Microprocessor Encounters an Interrupt:**
   1. **Interrupt Request (IRQ):** An external device sends an interrupt request to the 8086 microprocessor.
   2. **Interrupt Acknowledge:** The 8086 responds with an interrupt acknowledge signal (INTA).
   3. **Save Flags and CS/IP:** The current flags and the contents of the CS (Code Segment) and IP (Instruction Pointer) registers are pushed onto the stack.
   4. **Fetch Interrupt Vector:** The interrupt vector number is determined from the interrupt request, and the corresponding interrupt vector is fetched from the Interrupt Vector Table (IVT).
   5. **Update CS and IP:** The CS and IP are loaded with the values from the interrupt vector, pointing to the starting address of the interrupt service routine (ISR).
   6. **Execute ISR:** The microprocessor starts executing instructions from the ISR.
   7. **End of ISR:** At the end of the ISR, the flags, CS, and IP are restored from the stack to resume normal program execution.

(b) **Assembly Program (MASM) to Compare Two Numbers and Display a Message:**
```assembly
.model small
.data
    num1 db 5      ; First number
    num2 db 5      ; Second number
    equal_msg db 'Equal Numbers$'

.code
main proc
    ; Compare num1 and num2
    mov al, num1
    cmp al, num2

    ; Jump if not equal
    jne not_equal

    ; Display message if equal
    mov ah, 09h         ; DOS function to print string
    lea dx, equal_msg   ; Load address of the equal_msg string
    int 21h             ; Call interrupt 21h (DOS interrupt)

    ; Exit program
    mov ah, 4Ch         ; DOS function to exit program
    int 21h             ; Call interrupt 21h

not_equal:
    ; Handle case when numbers are not equal (you can add your code here)

main endp
end main
```


---


## **Questionn 3:**

**Hardware Control Logic (HCL):**
Hardware Control Logic (HCL) refers to the digital circuitry responsible for controlling various hardware components within a computer or electronic system. It plays a crucial role in coordinating the operation of different modules, managing data flow, and ensuring proper synchronization. HCL is implemented using digital logic circuits, such as gates, flip-flops, and other combinational and sequential logic elements.

**Gate Diagram of a Hardware Control Logic:**

A basic hardware control logic can be represented using gates and flip-flops. Let's consider a simple example of a control circuit with two inputs (A and B) and an output (Y).


Explanation:

1. **Inputs (A and B):** These represent signals or conditions that the control logic processes.
2. **AND Gate (G1):** The AND gate takes input signals A and B. The output is high (1) only when both A and B are high.
3. **NOT Gate (G2):** The NOT gate inverts the output of AND gate G1. It produces a high output (1) when G1's output is low, and vice versa.
4. **OR Gate (G3):** The OR gate combines the original inputs A and B with the inverted output of G2. The output is high if either A and B are high or G2 is low.
5. **Flip-Flop (FF1):** A flip-flop is used to store a binary state. It can be set (1) or reset (0) based on specific conditions. In this case, it is triggered by the output of OR gate G3.
6. **Output (Y):** The final output is taken from the Q output of the flip-flop.

**Operation Explanation:**

- If both A and B are high, G1 output is high, G2 output is low (inverted), and G3 output is high. This high signal sets FF1, and Y becomes high.
- If either A or B (or both) is low, G1 output is low, G2 output is high, and G3 output is high. This keeps FF1 in a reset state, and Y remains low.

This is a simplified representation, and real-world control logic can be significantly more complex, involving multiple inputs, conditions,
and sequential logic elements to manage the system's operation effectively.


---


## **Questionn 4:**

`Write a program in assembly language using procedures and ASCII codes, that will print small
alphabets on the screen using procedure name SMALI. and display capital alphabets on screen
using procedure name CAPITAL.`

```assembly
.model small
.data

.code
main proc
    ; Call procedure to print small alphabets
    call SMALI

    ; New line for better readability
    mov ah, 02h         ; DOS function to print character
    mov dl, 0Ah         ; ASCII code for newline
    int 21h             ; Call interrupt 21h (DOS interrupt)

    ; Call procedure to print capital alphabets
    call CAPITAL

    ; Exit program
    mov ah, 4Ch         ; DOS function to exit program
    int 21h             ; Call interrupt 21h
main endp

; Procedure to print small alphabets
SMALI proc
    mov ah, 02h         ; DOS function to print character

    mov dl, 'a'         ; ASCII code for 'a'
print_small:
    int 21h             ; Call interrupt 21h (DOS interrupt)

    inc dl              ; Move to the next alphabet
    cmp dl, 'z'         ; Check if 'z' is reached
    jle print_small     ; Jump if not reached
    ret
SMALI endp

; Procedure to print capital alphabets
CAPITAL proc
    mov ah, 02h         ; DOS function to print character

    mov dl, 'A'         ; ASCII code for 'A'
print_capital:
    int 21h             ; Call interrupt 21h (DOS interrupt)

    inc dl              ; Move to the next alphabet
    cmp dl, 'Z'         ; Check if 'Z' is reached
    jle print_capital   ; Jump if not reached
    ret
CAPITAL endp

end main
```

---


## **Questionn 5:**


### (a) **Difference between X86 and Y86 Instruction Set Architecture:**

**X86 Architecture:**
   - **Complexity:** X86 is a Complex Instruction Set Computing (CISC) architecture, which means it has a large set of instructions, some of which can perform complex operations.
   - **Variable-Length Instructions:** Instructions in X86 architecture can have variable lengths, making decoding more complex.
   - **Widely Used:** X86 is used in a variety of computing systems, including personal computers and servers.
   - **Addressing Modes:** Supports a rich set of addressing modes for flexibility.

**Y86 Architecture:**
   - **Simplicity:** Y86 is designed to be simpler and is often used for educational purposes. It follows the Reduced Instruction Set Computing (RISC) philosophy.
   - **Fixed-Length Instructions:** Instructions in Y86 have a fixed length, simplifying the instruction decoding process.
   - **Educational Use:** Y86 is not commonly used in mainstream systems but is employed in educational settings to teach computer architecture and assembly language programming.
   - **Limited Instructions:** Y86 has a smaller and more basic set of instructions compared to X86.

### (b) **Assembly Program for Fibonacci Series Sum in MASM:**

```assembly
.model small
.data
    fibonacci db 0, 1, 1, 2, 3    ; Fibonacci series
    result_msg db 'Sum of Fibonacci series: $'

.code
main proc
    mov ax, @data
    mov ds, ax

    mov ecx, 5      ; Number of elements in the Fibonacci series
    mov ebx, 0      ; Initialize sum to 0

    ; Loop to add the Fibonacci series elements
    add_loop:
        mov al, [fibonacci + ecx - 1] ; Load the current Fibonacci element
        add bl, al                     ; Add it to the sum
        loop add_loop                  ; Repeat for all elements

    ; Display the result on the screen
    mov ah, 09h         ; DOS function to print string
    lea dx, result_msg  ; Load address of the result_msg string
    int 21h             ; Call interrupt 21h (DOS interrupt)

    ; Display the result value
    mov ah, 02h         ; DOS function to print character
    add bl, '0'         ; Convert the sum to ASCII
    int 21h             ; Call interrupt 21h

    ; Exit program
    mov ah, 4Ch         ; DOS function to exit program
    int 21h             ; Call interrupt 21h

main endp
end main
```
