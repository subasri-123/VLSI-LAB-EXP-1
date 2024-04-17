# VLSI-LAB-EXPERIMENTS
AIM:
To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.2.

APPARATUS REQUIRED:
Vivado 2023.2

PROCEDURE:
STEP:1 Start the vivado software, Select and Name the New project.
STEP:2 Select the device family, device, package and speed.
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.
STEP:5 Select the run simulation adn then run Behavioral Simulation in the Source Window and click the check syntax.
STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
STEP:7 compare the output with truth table

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
## LOGIC GATES
```
module logic_gate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;  
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b); 
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
```
##  HALF ADDER
```
module HA(a,b,sum,carry);
input a,b;
output sum,carry;
endmodule
module multi_2(a,b,p,carry);
input [1:0]a,b;
output [2:0]p;
output carry;
endmodule
```
## FULL ADDER
```
module fa(a,b,c,sum,carry);
input a,b,c;
output sum,carry;
wire w1,w2,w3;
xor g1(w1,a,b);
and g2(w2,a,b);
xor g3(sum,w1,c);
and g4(w3,w1,c);
or g5(carry,w3,w2);
endmodule
```
## HALF SUBRACTOR
```
module hs(a,b,difference,borrow);
input a,b;
output difference,borrow;
wire w1;
xor g1(difference,a,b);
not g2(w1,a);
and g3(borrow,w1,b);
endmodule
```
## FULL SUBRACTOR
```
module fs(a,b,bin,d,bout);
input a,b,bin; 
output d,bout;
wire w1,w2,w3;
xor g1(w1,b,bin; 
xor g2(d,w1,a);
and g3(w2,a,~w1);
and g4(w3,~b,bin);
or g5(bout,w2,w3);
endmodule
```
## 8 BIT RIPPLE CARRY ADDER
```
module rca(a,b,c,sum,carry);
input [7:0]a,b;
input c;
output [7:0]sum;
output carry;
wire w1,w2,w3,w4,w5,w6,w7;
fa fa1(a[0],b[0],c,sum[0],w1);
fa fa2(a[1],b[1],w1,sum[1],w2);
fa fa3(a[2],b[2],w2,sum[2],w3);
fa fa4(a[3],b[3],w3,sum[3],w4);
fa fa5(a[4],b[4],w4,sum[4],w5);
fa fa6(a[5],b[5],w5,sum[5],w6);
fa fa7(a[6],b[6],w6,sum[6],w7);
fa fa8(a[7],b[7],w7,sum[7],carry);
endmodule
```

OUTPUT:
## LOGIC GATES
![logic gats](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/80d340e0-0deb-440c-8be1-5069b85a05b7)
## HALF ADDER
![ex-1 HA (2)](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/b63cf05f-757c-4cb9-bd17-4ccee6a96b51)
## FULL ADDER
![fa](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/0a3e7a3a-41f9-4b77-80f7-d960721b1755)
##  HALF SUBRACTER
![hs](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/92fd110f-853b-41de-942b-3b9af452500a)
## FULL SUBRACTOR
![fs](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/7d88da1b-33d5-49e5-8084-39d8971dae85)
## 8 BIT RIPPLE CARRY ADDER
![Screenshot (14)](https://github.com/subasri-123/VLSI-LAB-EXP-1/assets/166198549/9f2a0eda-e134-4dea-bf5e-10f70e08a30d)

RESULT:
Thus the simulation and synthesis of Logic Gates,Adders and Subtractors using vivado has been sucessfully executed and verified .

