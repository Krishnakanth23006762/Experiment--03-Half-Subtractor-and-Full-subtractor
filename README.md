# Experiment--03-Half-Subtractor-and-Full-subtractor
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

1.Use module projname(input,output) to start the Verilog programmming.

2.Assign inputs and outputs using the word input and output respectively.

3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.

4.Use each output to represnt onre for differnce and the other for borrow.

5.End the verilog program using keyword endmodule


## Program:

Half subtracter:
```
module hs(a,b,borrow,diff);
input a,b;
output diff,borrow;
assign diff=a^b;
assign borrow=~a&b;
endmodule
```

Full subtractor:
```
module hs(a,b,bin,borrow,diff);
input a,b,bin;
output diff,borrow;
assign diff=(a^b)^bin;
assign borrow=((~a)&&bin)||(b&&bin)||((~a)&&b);
endmodule
```



## Truthtable

Half subtracter:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/33e6577d-fe1a-4975-94a6-be994e6e6646)

Full subtractor:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/219e5278-c440-478d-8f3f-28fee7013cb2)


##  RTL realization

Half subtracter:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/725d2643-3751-4cf5-af2c-c8e285b2ca05)

Full subtractor:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/838a278f-07cc-4835-a0df-7a975bdb78c0)

## Timing diagram 

Half subtracter:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/19fe9f3b-ef08-4550-93cb-1c5c352c3a61)

Full subtractor:
![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/f5b5387d-ccdc-47e4-869e-8b75d29574e9)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
