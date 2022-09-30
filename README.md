# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
```
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: P.Ramsai
RegisterNumber:  212221240041

program 1:

USING NAND
module comblogic(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P = (~C&~B&~A);
assign Q = (~D&~C&~A);
assign R = (C&~(~B)&~A);
assign F= P&~Q&~R;
endmodule
program 2:

USING NOR
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule



```
## RTL realization
## Output:
## RTL:
## output1:
![Screenshot (145)](https://user-images.githubusercontent.com/94269989/193262421-856a6280-e3e4-4580-9084-1d72a275c277.png)

## Timing Diagram:
![Screenshot (146)](https://user-images.githubusercontent.com/94269989/193263000-f2c4a7eb-ce14-41e1-8f78-ed9859365ac5.png)

## truth table:
![Screenshot (147)](https://user-images.githubusercontent.com/94269989/193263124-6717f4d3-b516-4494-8fdf-c13cfbae7018.png)

## output2:
![Screenshot (148)](https://user-images.githubusercontent.com/94269989/193263249-1cce16e0-9745-4935-aaae-bfe03615217a.png)

## Timing diagram:

![Screenshot (146)](https://user-images.githubusercontent.com/94269989/193263419-de4870f8-0034-4848-97e3-1826d043c6ba.png)

## Truth table:
![Screenshot (147)](https://user-images.githubusercontent.com/94269989/193263702-99db5f12-8469-43ee-a344-89ed8c17c66b.png)


## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
