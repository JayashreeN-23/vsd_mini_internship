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





