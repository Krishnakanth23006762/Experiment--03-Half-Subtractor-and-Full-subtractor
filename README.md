
# Experiment--04-Half-Subtractor-and-Full-subtractor
# BY: B KRISHNAKANTH
# REFERENCE NUMBER: 23006762
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
module halfsub(diff,carry,x,y);
input x,y;
output diff,carry;
assign diff = x^y;
assign carry = ~x&y;
endmodule
```

Full subtractor:
```
module fullsub(diff,carry,a,b,c);
input a,b,c;
output diff,carry;
assign diff = a^b^c;
assign carry = (~a)&c | (~a)&b | (b&c);
endmodule
```



## Truthtable

Half subtracter:

![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/f5ca63e0-0629-4f37-83cc-62dd1f963515)


Full subtractor:


![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/331c8872-43cf-4bf2-8cb8-1c4178849e5b)


##  RTL realization

Half subtracter:

![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/7a379873-05fb-40a2-a4da-9f80d68d03f0)

Full subtractor:

![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/3ad025c2-6448-41d2-8b2e-3ae7ccca514c)


## Timing diagram 

Half subtracter:

![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/ef4eb6ed-15fe-4474-9d32-1634836126ab)


Full subtractor:

![image](https://github.com/Krishnakanth23006762/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/138849446/a8b00242-0471-4489-b454-1e4abe7839c7)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
