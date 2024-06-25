# vsd_mini_internship
# Task 1:  Using a RISC-V simulator, write a C program to count the sum of all numbers from 1 to n.
1. I have started with the installation of the oracle virtual box
![Virtual box installation](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/e0fd0241-6ee6-4037-9cc0-c1509c951068)
2. Then I have installed ubuntu
![Installation of Ubuntu](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f91d03bd-8764-4564-87f1-87700c9db623)
3. I started by opening Terminal and creating and opening a new C file in Leafpad and named it as sum1ton.c . I wrote the code in it as shown in below image.
![C program for sum of numbers from 1 to n](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/abc7ffdf-40eb-485f-8067-5292b8a11dbf)
4. After that, it was compiled, run in the terminal to verify, and the desired output was obtained.
![output of the c program](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/f034395c-6198-48b2-aae6-eae609a3143e)
# Running the same program in the RISC-V Simulator
After running the code in the terminal, I needed to run it in the RISC-V simulator. To do that, I was required to run a specific set of code, which I completed in the steps below:
1. In order to produce a file with the ".o" extension(Assembled File), I first wrote the code to build it using the RISC-V gcc compiler with 'O1' as compiler option.Then the outuput will be,
![Assembly code](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/b767dd45-4ac1-4a04-86b8-141944c51bc4)

3. Next To obtain the assembly code for the aforementioned C program, I wrote the code riscv-unknown-elf-objdump -d sum1ton.o. I received many assembly codes in return. Merely by appending "| less" to the command, the number of assembly codes shown were lowered. I searched the "main" section to get the instructions for our main code.
![Main function](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/933d40d7-bde3-4bb7-b988-4b4cc19c42a2)

5. After this I run the identical instructions with a different parameter, instead of O1, I used Ofast. I didn't observed any changes in the instructions.
![Fast instruction](https://github.com/JayashreeN-23/vsd_mini_internship/assets/173695325/64b037c5-8e0a-4db1-b439-51001dfbbc87)
# Task 1 completed

# Task 2: Using a RISC-V simulator, write a C program for the smart elevator.
# My project is to create the smart elevator controller.
Before writing the code first we should understand about "SMART ELEVATOR CONTROLLER" and how does it work. Once we understand how does it works we can develop the driver to run it very easily.
# Elevator Working Process
Elevator Working Process
# Initialization: 
The elevator is initialized at floor 0, with no target and in an IDLE state.
# Request Handling:
A request is made to move to floor 5.
The target floor is set to 5.
The direction is set to UP because the current floor (0) is less than the target floor (5).
# Movement: 
The elevator moves floor by floor:
The direction is UP, so the elevator increments the current floor by 1 in each iteration.
After each move, the current floor is printed.
# Reaching the Target:
When the elevator reaches floor 5:
The direction is set to IDLE.
The request is cleared.
The final message is printed indicating that the elevator has reached the target floor.
This simple model effectively demonstrates the fundamental logic behind an elevator controller.

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

# Task 2 completed












