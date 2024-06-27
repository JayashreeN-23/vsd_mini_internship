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
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
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
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
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
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  </details>





















