# vsd_mini_internship
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<details>

<summary><h3>Task 1: </h3> Using a RISC-V simulator, write a C program to count the sum of all numbers from 1 to n</summary>

1. I have started with the installation of the oracle virtual box
![Virtual box installation](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/e0fd0241-6ee6-4037-9cc0-c1509c951068)
2. Then I have installed ubuntu
![Installation of Ubuntu](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f91d03bd-8764-4564-87f1-87700c9db623)
3. I started by opening Terminal and creating and opening a new C file in Leafpad and named it as sum1ton.c . I wrote the code in it as shown in below image.
![C program for sum of numbers from 1 to n](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/abc7ffdf-40eb-485f-8067-5292b8a11dbf)
4. After that, it was compiled, run in the terminal to verify, and the desired output was obtained.
![output of the c program](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f034395c-6198-48b2-aae6-eae609a3143e)

**Running the same program in the RISC-V Simulator**
  
After running the code in the terminal, I needed to run it in the RISC-V simulator. To do that, I was required to run a specific set of code, which I completed in the steps below:
1. In order to produce a file with the ".o" extension(Assembled File), I first wrote the code to build it using the RISC-V gcc compiler with 'O1' as compiler option.Then the outuput will be,
![Assembly code](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/b767dd45-4ac1-4a04-86b8-141944c51bc4)

3. Next To obtain the assembly code for the aforementioned C program, I wrote the code riscv-unknown-elf-objdump -d sum1ton.o. I received many assembly codes in return. Merely by appending "| less" to the command, the number of assembly codes shown were lowered. I searched the "main" section to get the instructions for our main code.
![Main function](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/933d40d7-bde3-4bb7-b988-4b4cc19c42a2)

5. After this I run the identical instructions with a different parameter, instead of O1, I used Ofast. I didn't observed any changes in the instructions.
![Fast instruction](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/64b037c5-8e0a-4db1-b439-51001dfbbc87)
**Task 1 completed**

</details>

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



<details>

<summary><h3>Task 2: </h3> Using a RISC-V simulator, write a C program for the smart elevator</summary>

**My project is to create the smart elevator controller.**
Before writing the code first we should understand about "SMART ELEVATOR CONTROLLER" and how does it work. Once we understand how does it works we can develop the driver to run it very easily.

**Elevator Working Process**

**Initialization:** The elevator is initialized at floor 0, with no target and in an IDLE state.

**Request Handling:** A request is made to move to floor 5.The target floor is set to 5.The direction is set to UP because the current floor (0) is less than the target floor (5).

**Movement:**  The elevator moves floor by floor:The direction is UP, so the elevator increments the current floor by 1 in each iteration.
After each move, the current floor is printed.

**Reaching the Target:** When the elevator reaches floor 5:
The direction is set to IDLE.
The request is cleared.
The final message is printed indicating that the elevator has reached the target floor.
This simple model effectively demonstrates the fundamental logic behind an elevator controller.

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/2a1f1fa9-99c7-40d6-8c14-e7a981e1adfd)


1.I started by opening Terminal and creating and opening a new C file in Leafpad and named it as smart_elevator.c , I wrote the code in it as the below image,
![Screenshot 2024-06-25 150957](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/b6f73d91-8752-40c4-8a42-53364e64534e)
![Screenshot 2024-06-25 151010](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/45c243ca-b4e6-46d5-80df-b521e60d04a6)

2. After that, it was compiled, run in the terminal to verify, and the desired output was obtained.
![Screenshot 2024-06-25 152802](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/b3cb6a37-75fd-4a8f-a8ff-6438f0c95e65)

3. In order to produce a file with the ".o" extension(Assembled File), I first wrote the code to build it using the RISC-V gcc compiler with 'O1' as compiler option.Then the outuput will be,
![Screenshot 2024-06-25 153410](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/60129b86-f730-4c9f-8292-edfaaaa619db)
![Screenshot 2024-06-25 153609](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/5fa14355-9c23-4944-a543-f295767b50ee)

4. Next To obtain the assembly code for the aforementioned C program, I wrote the code riscv-unknown-elf-objdump -d sum1ton.o. I received many assembly codes in return. Merely by appending "| less" to the command, the number of assembly codes shown were lowered. I searched the "main" section to get the instructions for our main code.
![Screenshot 2024-06-25 153717](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/d1790c19-4490-46d9-9429-572b12bf3e95)

5. Then the main function and the output is given by,
![Screenshot 2024-06-25 154420](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/88e5c4c7-3c12-4b23-9d4a-6a635e877221)

**Task 2 completed**

</details>

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


<details>

<summary><h3>Task 3: </h3> Do SPIKE Simulation and verification with -O1 and -Ofast along with running the RISC-V. </summary>

In this task, we have to perform Spike Simulation and observe with (`-o1`) and (`-ofast`) command.

####  Verification with `-o1` command :

At first, we will verify the code for `-o1` , to do that, the output we got from the `gcc` command should be equal to the spike simulation.

This command ` riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o smart_elevator.o smart_elevator.c ` will run the C code to give the output in C by using `./a.out` and for RISC-V processor we must use `spike pk smart_elevator`

Hence, the verification for command `-o1` is done.

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/deea60dd-2fc9-4e66-8470-09008568eb9b)


##### Debugging the RISC-V Processor for `-o1` using Spike simulation :

Now we will debugg the assembly code instruction we got from from ` riscv64-unknown-elf-objdump -d vending_machine.o | less `

![Screenshot 2024-06-27 125157](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/c864156f-35f3-445b-a07a-83a3bac345d4)

In this, we will debugg by using the instruction `spike -d pk vending_machine` 
which will allow us to spike any instruction we want.

Now, we spike for the initial address we see on the assembly code `100b0` so that we can see starting address to any point manually by using program counter

To do so, `until pc 0 100b0`, this means that it will debugg all the instruction after 100b0 and also shows the previous instructions to `100b0` is already being debugged. 

Type for `reg 0 a2`, it will show the register value at zero core for a2 operand.
To see next instruction, press `Enter` and it will show the starting address and if pressed again it will go to `100b4` which is the next instruction.

`reg 0 sp` shows the stack pointer of the instruction of 100b4

and if we want to see the next instruction(`100b8`) stack pointer just subtract the value we got from `reg 0 sp` of `100b4` from `16` as it is a hexadecimal value. It will give the `100b8` instruction stack pointer.
We can verify it by using `until pc 0 100b8` the program counter poites at instruction `100b8`, before that quit from the previous operation by pressing `q`.

Type `reg 0 sp`
Hence it is verified and debugged now.

##### Verification with `-ofast` :
Step 1: C Code compilation using command ` riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o smart_elevator.o smart_elevator.c `.
Check the output by running `gcc file_name` which is `gcc smart_elevator.c`
The output can be verified by using `./a.out`

Step 2: RISC-V Processor compilation is by using again ` riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o smart_elevator.o smart_elevator.c `.
Check and verified the output by `spike pk smart_elevator.o`.

- Note: If the ouput from Step 1 and Step 2 is matched, then the verification with `-ofast` is over.

  ![Screenshot 2024-06-27 124540](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/ecf441a9-7e46-48d2-9d3d-3fd7718477ab)

  ![Screenshot 2024-06-27 130806](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/30302a6d-5c4a-4745-b4a1-4c46fa559184)

  **Task 3 completed**
  
  </details>

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<details>

<summary><h3>Task 4: </h3>Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions. </summary>

To identify the 32-bit instruction code for each RISC-V instruction, we need to understand the format for each type of instruction: R, I, S, B, U, and J.

Here are the formats:

### R-Type Format
- *Opcode:* 7 bits
- *rd:* 5 bits (destination register)
- *funct3:* 3 bits
- *rs1:* 5 bits (source register 1)
- *rs2:* 5 bits (source register 2)
- *funct7:* 7 bits

### I-Type Format
- *Opcode:* 7 bits
- *rd:* 5 bits (destination register)
- *funct3:* 3 bits
- *rs1:* 5 bits (source register 1)
- *imm:* 12 bits (immediate value)

### S-Type Format
- *Opcode:* 7 bits
- *imm[4:0]:* 5 bits (immediate value)
- *funct3:* 3 bits
- *rs1:* 5 bits (source register 1)
- *rs2:* 5 bits (source register 2)
- *imm[11:5]:* 7 bits (immediate value)

### B-Type Format
- *Opcode:* 7 bits
- *imm[11]:* 1 bit (immediate value)
- *imm[4:1]:* 4 bits (immediate value)
- *funct3:* 3 bits
- *rs1:* 5 bits (source register 1)
- *rs2:* 5 bits (source register 2)
- *imm[10:5]:* 6 bits (immediate value)
- *imm[12]:* 1 bit (immediate value)

### U-Type Format
- *Opcode:* 7 bits
- *rd:* 5 bits (destination register)
- *imm[31:12]:* 20 bits (immediate value)

### J-Type Format
- *Opcode:* 7 bits
- *rd:* 5 bits (destination register)
- *imm[19:12]:* 8 bits (immediate value)
- *imm[11]:* 1 bit (immediate value)
- *imm[10:1]:* 10 bits (immediate value)
- *imm[20]:* 1 bit (immediate value)

Now, let's write the 32-bit instruction codes for each instruction:

### R-Type Instructions
- *ADD r1, r2, r3*
  - *funct7*: 0000000
  - *rs2*: r3 (0011)
  - *rs1*: r2 (0010)
  - *funct3*: 000
  - *rd*: r1 (0001)
  - *opcode*: 0110011

  *Binary:* 0000000 0011 0010 000 0001 0110011
  *Hex:* 0x00208133

- *SUB r3, r1, r2*
  - *funct7*: 0100000
  - *rs2*: r2 (0010)
  - *rs1*: r1 (0001)
  - *funct3*: 000
  - *rd*: r3 (0011)
  - *opcode*: 0110011

  *Binary:* 0100000 0010 0001 000 0011 0110011
  *Hex:* 0x40210133

- *AND r2, r1, r3*
  - *funct7*: 0000000
  - *rs2*: r3 (0011)
  - *rs1*: r1 (0001)
  - *funct3*: 111
  - *rd*: r2 (0010)
  - *opcode*: 0110011

  *Binary:* 0000000 0011 0001 111 0010 0110011
  *Hex:* 0x00317133

- *OR r8, r2, r5*
  - *funct7*: 0000000
  - *rs2*: r5 (0101)
  - *rs1*: r2 (0010)
  - *funct3*: 110
  - *rd*: r8 (1000)
  - *opcode*: 0110011

  *Binary:* 0000000 0101 0010 110 1000 0110011
  *Hex:* 0x0050A233

- *XOR r8, r1, r4*
  - *funct7*: 0000000
  - *rs2*: r4 (0100)
  - *rs1*: r1 (0001)
  - *funct3*: 100
  - *rd*: r8 (1000)
  - *opcode*: 0110011

  *Binary:* 0000000 0100 0001 100 1000 0110011
  *Hex:* 0x0040A233

- *SLT r10, r2, r4*
  - *funct7*: 0000000
  - *rs2*: r4 (0100)
  - *rs1*: r2 (0010)
  - *funct3*: 010
  - *rd*: r10 (1010)
  - *opcode*: 0110011

  *Binary:* 0000000 0100 0010 010 1010 0110011
  *Hex:* 0x004152B3

### I-Type Instructions
- *ADDI r12, r3, 5*
  - *imm*: 000000000101
  - *rs1*: r3 (0011)
  - *funct3*: 000
  - *rd*: r12 (1100)
  - *opcode*: 0010011

  *Binary:* 000000000101 0011 000 1100 0010011
  *Hex:* 0x00518193

- *LW r13, r11, 2*
  - *imm*: 000000000010
  - *rs1*: r11 (1011)
  - *funct3*: 010
  - *rd*: r13 (1101)
  - *opcode*: 0000011

  *Binary:* 000000000010 1011 010 1101 0000011
  *Hex:* 0x0025A293

### S-Type Instructions
- *SW r3, r1, 4*
  - *imm*: 000000000100
  - *rs1*: r1 (0001)
  - *rs2*: r3 (0011)
  - *funct3*: 010
  - *opcode*: 0100011

  *Binary:* 0000000 0011 0001 010 0010 0011 0010
  *Hex:* 0x00412023

### B-Type Instructions
- *BNE r0, r1, 20*
  - *imm*: 000000001010
  - *rs1*: r0 (0000)
  - *rs2*: r1 (0001)
  - *funct3*: 001
  - *opcode*: 1100011

  *Binary:* 000000 1 00001 0000 001 0 0100 000 1100011
  *Hex:* 0x01408063

- *BEQ r0, r0, 15*
  - *imm*: 000000000111
  - *rs1*: r0 (0000)
  - *rs2*: r0 (0000)
  - *funct3*: 000
  - *opcode*: 1100011

  *Binary:* 000000 0 00000 0000 000 1 1110 000 1100011
  *Hex:* 0x01E08063

### U-Type Instructions
- None in this list

### J-Type Instructions
- None in this list

**Task 4 completed**

</details>

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<details>

<summary><h3>Task 5:</h3>Using RISC-V Core Verilog netlist and testbench for functional simulation experiment.In this we need to find the output waveforms for the instructions which we learnt in Task 4.</summary>

Follow the steps to obtain the waveform for the instructions used in Task 4.

> The Verilog Code and Testbench used is refered by https://github.com/vinayrayapati/rv32i/

1.Firstly give the command: 
```
                            sudo apt-get update
                            sudo apt-get install iverilog gtkwave
```
2.etup Your Project Directory Create a directory for your project and place your Verilog files and testbench there. 
```
                   mkdir rv 
                   cd rv 
```                              
3. Copy the code from the reference code and paste it in a file name under `rv_riscv32.v` and `rv_riscvtb.v`

4. Give command line as `touch rv_riscv32.v` and  `touch rv_riscvtb.v`  in leafpad
   
5. Run and simulate the verilog code by using the below command;

```
                                 iverilog -o rv_riscv32 rv_riscv32.v rv_riscvtb.v
                                ./rv_riscv32
```

6.View the Waveform Open the waveform file using GTKWave:
```
                                 gtkwave iiitb_rv32i.vcd

```
7.Then GTKWave will open 
![b8myq9jp](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/29e685c2-679e-46d8-8c5b-d799cfa23412)

![WhatsApp Image 2024-07-08 at 17 21 07_ce3a29ac](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/d44df211-92dc-4a4a-b23c-319e8780d100)

8.Now, drag the command in the same way presented under ` time ` section.

Select the instructions from EX_MEM_IR[31:0] to present the instructions used in Task 4.

**Instruction ADD r1, r2, r3 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f84ef554-6925-461a-961a-b05ee1165f4f)

**Instruction SUB r3, r1, r2 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/2554116f-8cfb-46f1-b95a-1744f4c6937c)

**Instruction AND r2, r1, r3 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/63ca2759-c8cd-4c77-91cc-3e2bd4df667d)

**Instruction OR r8, r2, r5 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/8a4f50b8-58a0-4429-b6cd-61e0cceee3f2)

**Instruction XOR r8, r1, r4 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/04cf7b43-6288-4aca-afe9-6ff9fdd06f76)

**Instruction SLT r10, r2, r4 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/637b73c5-87a5-4a29-8e42-c0c57e0581e8)

**Instruction ADDI r12, r3, 5 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/51acecc9-3ecd-41a9-a6bd-6d9cb05a6640)

**Instruction SW r3, r1, 4 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f1dd8936-8675-4515-9077-32bb3974c390)

**Instruction SRL r16, r11, r2 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/6c233374-0dc8-4809-a481-f55ff3b3e11f)

**Instruction BNE r0, r1, 20 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/9ff296ce-a643-4e9a-9da7-2e59263abb94)

**Instruction SLL r15, r11, r2 :**

![image](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/eb5935ed-3c8c-4428-ad2e-ba764ac563fe)

**Task 5 completed**

</details>

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
<details>

<summary><h3>Task 6: </h3>To give the overview,components required,pin diagram of the smart elevator. </summary>

# Smart Elevator Controller Using VSDsquadron Mini
## Overview
Sure! Here’s a simplified version of the smart elevator project using a 16x2 LCD with an I2C interface, a 4x4 keypad, push buttons, and the VSDsquadron Mini board.

### Components Required
1. *VSDsquadron Mini board*
2. *16x2 LCD Display with I2C Module*
3. *4x4 Keypad*
4. *Breadboard and Jumper Wires*
5. *USB Cable for Power and Data*

### Pin Connections
#### LCD with I2C Connections
- *VCC*: Connect to +5V
- *GND*: Connect to GND
- *SDA*: Connect to I2C SDA pin (e.g., GPIO PC1)
- *SCL*: Connect to I2C SCL pin (e.g., GPIO PC2)

#### Keypad Connections
- *Row Pins (R1-R4)*: Connect to GPIO pins D0, D1, D2, D3
- *Column Pins (C1-C4)*: Connect to GPIO pins D4, D5, D6, D7


### Simplified Process

1. *Connect the LCD*:
   - *Power*: VCC to +5V, GND to GND
   - *I2C Data*: SDA to PC1, SCL to PC2

2. *Connect the Keypad*:
   - *Rows*: R1 to D0, R2 to D1, R3 to D2, R4 to D3
   - *Columns*: C1 to D4, C2 to D5, C3 to D6, C4 to D7

3. *Power and Data Connection*:
   - Connect the VSDsquadron Mini board to the computer using a USB cable for both power and data communication.

### Sample Code

Here’s a sample code to get you started. This code initializes the LCD, keypad. It will display the keypad input on the LCD.


```
#include <debug.h>
#include <ch32v00x.h>
#include <ch32v00x_gpio.h>

// Define pin connections for the keypad
#define KEYPAD_ROW1 GPIO_Pin_4
#define KEYPAD_ROW2 GPIO_Pin_5
#define KEYPAD_ROW3 GPIO_Pin_6
#define KEYPAD_ROW4 GPIO_Pin_7
#define KEYPAD_COL1 GPIO_Pin_0
#define KEYPAD_COL2 GPIO_Pin_1
#define KEYPAD_COL3 GPIO_Pin_2
#define KEYPAD_COL4 GPIO_Pin_3

// I2C LCD Address
#define LCD_ADDRESS 0x27

void delay(uint32_t count) {
    while (count--) {
        __asm("nop");
    }
}

void GPIO_Config(void) {
    GPIO_InitTypeDef GPIO_InitStructure;

    // Enable GPIO clocks
    RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOA, ENABLE);

    // Configure keypad row pins as output
    GPIO_InitStructure.GPIO_Pin = KEYPAD_ROW1 | KEYPAD_ROW2 | KEYPAD_ROW3 | KEYPAD_ROW4;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(GPIOA, &GPIO_InitStructure);

    // Configure keypad column pins as input with pull-up resistors
    GPIO_InitStructure.GPIO_Pin = KEYPAD_COL1 | KEYPAD_COL2 | KEYPAD_COL3 | KEYPAD_COL4;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU;
    GPIO_Init(GPIOA, &GPIO_InitStructure);
}

char readKeypad(void) {
    // Scan keypad rows
    for (int row = 0; row < 4; row++) {
        GPIO_ResetBits(GPIOA, KEYPAD_ROW1 | KEYPAD_ROW2 | KEYPAD_ROW3 | KEYPAD_ROW4);
        GPIO_SetBits(GPIOA, (KEYPAD_ROW1 << row));
        delay(10000);

        if (GPIO_ReadInputDataBit(GPIOA, KEYPAD_COL1) == Bit_RESET) return '1' + row * 4;
        if (GPIO_ReadInputDataBit(GPIOA, KEYPAD_COL2) == Bit_RESET) return '2' + row * 4;
        if (GPIO_ReadInputDataBit(GPIOA, KEYPAD_COL3) == Bit_RESET) return '3' + row * 4;
        if (GPIO_ReadInputDataBit(GPIOA, KEYPAD_COL4) == Bit_RESET) return '4' + row * 4;
    }
    return '\0';
}

void I2C_Config(void) {
    I2C_InitTypeDef I2C_InitStructure;

    // Enable I2C clock
    RCC_APB1PeriphClockCmd(RCC_APB1Periph_I2C1, ENABLE);

    // I2C configuration
    I2C_InitStructure.I2C_Mode = I2C_Mode_I2C;
    I2C_InitStructure.I2C_DutyCycle = I2C_DutyCycle_2;
    I2C_InitStructure.I2C_OwnAddress1 = 0x00;
    I2C_InitStructure.I2C_Ack = I2C_Ack_Enable;
    I2C_InitStructure.I2C_AcknowledgedAddress = I2C_AcknowledgedAddress_7bit;
    I2C_InitStructure.I2C_ClockSpeed = 100000;
    I2C_Init(I2C1, &I2C_InitStructure);

    // Enable I2C
    I2C_Cmd(I2C1, ENABLE);
}

void I2C_Write(uint8_t address, uint8_t data) {
    // Send I2C start signal
    I2C_GenerateSTART(I2C1, ENABLE);
    while (!I2C_CheckEvent(I2C1, I2C_EVENT_MASTER_MODE_SELECT));

    // Send I2C address
    I2C_Send7bitAddress(I2C1, address, I2C_Direction_Transmitter);
    while (!I2C_CheckEvent(I2C1, I2C_EVENT_MASTER_TRANSMITTER_MODE_SELECTED));

    // Send data
    I2C_SendData(I2C1, data);
    while (!I2C_CheckEvent(I2C1, I2C_EVENT_MASTER_BYTE_TRANSMITTING));

    // Send I2C stop signal
    I2C_GenerateSTOP(I2C1, ENABLE);
}

void LCD_SendCommand(uint8_t cmd) {
    // Send command to the LCD
    I2C_Write(LCD_ADDRESS, cmd);
    delay(5000);
}

void LCD_Init(void) {
    // Initialize the LCD
    delay(50000);  // Wait for LCD to power up

    LCD_SendCommand(0x30);  // Function set
    delay(5000);
    LCD_SendCommand(0x30);  // Function set
    delay(5000);
    LCD_SendCommand(0x30);  // Function set
    delay(5000);
    LCD_SendCommand(0x20);  // Set to 4-bit mode
    delay(5000);

    // Configure the LCD
    LCD_SendCommand(0x28);  // Function set: 4-bit, 2 line, 5x8 dots
    LCD_SendCommand(0x08);  // Display off
    LCD_SendCommand(0x01);  // Clear display
    delay(5000);
    LCD_SendCommand(0x06);  // Entry mode set: increment automatically, no display shift
    LCD_SendCommand(0x0C);  // Display on, cursor off, blink off
}

void LCD_Print(char* message) {
    while (*message) {
        I2C_Write(LCD_ADDRESS, *message++);
        delay(5000);
    }
}

int main(void) {
    // System initialization
    SystemInit();
    debug_init();

    // GPIO configuration
    GPIO_Config();

    // I2C configuration
    I2C_Config();

    // LCD initialization
    LCD_Init();

    while (1) {
        char key = readKeypad();
        if (key) {
            // Print the key pressed to the LCD
            char message[2] = { key, '\0' };
            LCD_Print(message);
            LCD_Print("**Floor**");
        }
        delay(100000);
    }
}

```

### Task 6 completed

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<details>

<summary><h3>Task 7: </h3> Demonstration of the project</summary>
  
# Circuit Connections

![WhatsApp Image 2024-07-17 at 14 36 39_810e7109](https://github.com/user-attachments/assets/1166c37a-e3c0-49c8-a015-5e2cdbe958c1)

#  Application Video












