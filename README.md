 AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
 Equipments Required:
 Hardware – PCs, Cyclone II , USB flasher
 Software – Quartus prime


 Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

 Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

 Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

 Logic Diagram
 Procedure
 Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

COMBINATION 1 USING NAND GATE

module combone(A,B,C,D,F);

input A,B,C,D;

output F;

wire P,Q,R;

assign P=(~(~C & B & A));

assign Q=(~(~D & C & A));

assign R=(~(C & ~B & A));

assign F=~(P & Q & R);

endmodule

COMBINATION 2 USING NOR GATE

module combtwo(A,B,C,D,F);

input A,B,C,D;

output F;

wire P,Q,R,S;

assign P = (C & ~B & A);

assign Q = (D & ~C & A);

assign R = (C & ~B & A);

assign S = (~(P | Q | R));

assign F = (~s);

endmodule

Developed by: S.RENUGA
RegisterNumber: 22008594 

COMBINATION 1

 RTL realization

 Output:
 
 ![RTL 2](https://user-images.githubusercontent.com/119292258/211195146-db2f3faa-ac84-48b9-8cb3-39cab2ed13b9.png)

TIMING DIAGRAM

 ![Screenshot (28)](https://user-images.githubusercontent.com/119292258/211195229-61ca2cb6-b0ef-42f5-8653-374cd6aa3b1b.png)

 TRUTH TABLE
 
 ![T](https://user-images.githubusercontent.com/119292258/211195243-29ca20ab-8d00-40ea-b910-fa5cc1014a18.png)

 COMBINATION 2
 
 RTL REALIZATION
 
 ![RTL 2](https://user-images.githubusercontent.com/119292258/211195319-39e9f9fb-c25f-487a-aac2-5bc4cc1ef57b.png)
 
TIMING DIAGRAM

 ![TD](https://user-images.githubusercontent.com/119292258/211195341-27991230-880e-4544-9197-d14370f0d065.png)

TRUTH TABLE

![truth table](https://user-images.githubusercontent.com/119292258/211195360-adf63bc2-5ab7-4793-90d8-b6f1d00d67cf.png)


 Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
