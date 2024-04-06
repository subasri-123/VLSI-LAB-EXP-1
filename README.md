# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

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
# Logic gates
```
module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
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
# Half Adder
```
module ha(a,b,sum,carry);
input a,b;
output sum,carry;
endmodule
module multi_2(a,b,p,carry);
input [1:0]a,b;
output [2:0]p;
output carry;
endmodule
```
# Half Subtractor
```
module halfsubtractor(a,b,diff,borrow);
input a,b;
output diff,borrow;
xor g1(diff,a,b);
and g2(borrow,~a,b);
endmodule
```
# Full Adder
```
module fadd(a,b,c,sum,carry);
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
# Full Subtractor
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
# 8 bit Ripple Carry Adder
```
module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule
```

OUTPUT:
# Logic gates
# And Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/63457dad-a0fa-42c0-9ded-592f585c0e04)
# Or Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/f03c5f10-1de7-4197-b45a-d243f64b5d3d)
# Nand Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/c4f55516-fbdb-4ed7-9c36-39dbe3d6fb73)
# Nor Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/ded32bb6-7e78-4b90-9527-471340dd7e11)
# Xor Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/3e32a016-4b59-4c98-b931-2057e78361de)
# Xnor Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/6f7cfb61-6c20-4b77-9a29-02f524f20cb6)
# Not Gate
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/2e224bfc-04ac-420e-a70b-8044d9504d94)
# Half Adder
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/3a9775e0-6c38-4cbf-9a75-4bfb552c4d3b)
# Half Subtractor
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/bf72a1f8-8a5f-439b-a9e8-f28362433d3e)
# Full Adder
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/92f26ec4-58ce-46ea-816f-9e468d2685ac)
# Full Subtractor
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/752b404d-0c8d-4c9d-a921-9bdbcaf3e8db)
# 8 Bit Ripple Carry Adder
![image](https://github.com/Binnu-123/VLSI-LAB-EXP-1/assets/161333609/b7dd8aec-fbf7-40a2-a94a-76b10bc3fb31)



RESULT:

Hence Logic Gates,Adders and Subtractor are simulated and synthesised using Xilinx ISE.
