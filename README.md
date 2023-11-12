# Experiment--04-Half-Subtractor-and-Full-subtractor
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

STEP 1: Use module project name(input,output) to start the Verilog programmming.

STEP 2: Assign inputs and outputs using the word input and output respectively.

STEP 3: Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

STEP 4: Use each output to represnt onre for differnce and the other for borrow.

STEP 5: End the verilog program using keyword endmodule.

 


## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.

Developed by: SIVAMOHANASUNDARAM. V

RegisterNumber: 212222230145

```
## Halfsubtractor:

module EX04(a,b,difference,borrow);

input a,b;

output difference,borrow;

wire x;

xor (difference,a,b);

not (x,a);

and (borrow,x,b);

endmodule

## Fullsubtractor:

module FullSub04(a,b,bin,difference,borrow);

input a,b,bin;

output difference,borrow;

wire p;

assign difference=((a^b)^bin);

not (p,a);

assign borrow=((p&b)|(p&bin)|(b&bin));

endmodule

## Output:

## Truthtable

Halfsubtractor:

![exp45](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/209500d3-2760-482c-94c4-81c9c586dcd4)

Fullsubtractor:

![exp46](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/8511bcf6-c04d-43d2-a2a5-36bc079745dd)

##  RTL realization
Halfsubtractor:
![exp44](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/1cc1a497-df76-415c-b20b-63f9dda5ca12)


Fullsubtractor:
![exp43](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/4a073916-7b92-438d-acf3-7cb0ae95922b)


## Timing diagram 
Halfsubtractor:
![one](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/ffff50e8-7042-492c-a3ff-4cac811491a0)

Fullsubtractor:
![two](https://github.com/dhivyapriyar/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119477552/927ff18e-695b-4399-8bba-f6d92084e079)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
