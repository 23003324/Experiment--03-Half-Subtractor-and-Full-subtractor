NAME : HARITHA RAMESH
REGISTER NO:23003324
# Experiment 03 Half Subtractor and Full subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
1. Create a New Project:
   - Open Quartus and create a new project by selecting "File" > "New Project Wizard."
   - Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).

2. Create a New Design File:
   - Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
   - Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.

3. Write the Combinational Logic Code:
   - Open the newly created Verilog or VHDL file and write the code for your combinational logic.
     
4. Compile the Project:
   - To compile the project, click on "Processing" > "Start Compilation" in the menu.
   - Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.

5. Analyze and Fix Errors:*
   - If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
   - Review and fix any issues in your code if necessary.
   - View the RTL diagram.

6.*Verification:
   - Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
   - Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
   - Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.



### HALF SUBRACTOR


## Program:
## HALF SUBTRACTOR
module halfsub(x,y,D,B);

input x,y;

output D,B;

wire xbar;

xor(D,x,y);

not(xbar,x);

and(B,xbar,y);

endmodule 

## FULL SUBTRACTOR
module FS(output D,B,input x,y,z);

assign D =x^y^z;

assign B =~x&(y^z)|y&z;

endmodule 

### RTL REALIZATION
## HALF SUBTRACTOR

![HS RTL](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/b66effa2-b83a-41ab-af79-ed0d448422fd)
 ## FULL SUBTRACTOR
 ![FS RTL](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/bc447a53-3707-44ae-8ba9-d6f975a4dd4b)


### TRUTH TABLE
## HALF SUBTRACTOR
![HS TT](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/71381bb1-4224-4c90-8298-10ce64790594)
## FULL SUBTRACTOR
![FS TT](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/8b65e0a5-7ae6-48a2-86d4-114ef305184f)


### WAVEFORM
## HALF SUBTRACTOR
![wf hs](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/f20b8ce4-3648-443c-98e5-5f8f213a12ab)
## FULL SUBTRACTOR
![WF FS](https://github.com/23003324/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/140035234/66065dff-e92c-4197-a4e9-631b31e6b34a)



## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
