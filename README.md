EXP.NO: 02    

DATE: 27/02/2024

SIMULATION AND IMPLEMENTATION OF
COMBINATIONAL CIRCUITS


AIM: 

To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using Vivado. 

APPARATUS REQUIRED:
                          			VIVADO 2023.2 

PROCEDURE:

STEP:1 Start the Vivado, Select and Name the New project. 

STEP:2 Select the device family, device, package and speed. 

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table

ENCODER:                 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/fb34665a-8c8b-46ac-8a8f-0145f5be6077)



PROGRAM: 

module encoder (d, a0, a1, a2); 

input [7:0] d; 

output a0, a1, a2; 

assign a2=d[7] |d[6] |d[5] |d[4]; 

assign a1=d[7] |d[6] |d[3] |d[2]; 

assign a0=d[7] |d[5] |d[3] |d[1]; 

endmodule 

OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/9e6dcd41-8f7d-4970-8da0-ecf0d53488cf)
 

DECODER:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/97d1b6d4-8659-4a62-843c-b082bb49faa9)






PROGRAM: 

module decoder (s, y); 

input [2:0] s; 

output [7:0] y; 

assign y[0]=~s[2] & ~s[1] & ~s[0]; 

assign y[1]=~s[2] &~s[1] & s[0]; 

assign y[2]=~s[2] & s[1] &~s[0]; 

assign y[3]=~s[2] & s[1] & s[0]; 

assign y[4]=s[2] & ~s[1] & ~s[0]; 

assign y[5]=s[2] & ~s[1] & s[0]; 

assign y[6]=s[2] & s[1] & ~s[0]; 

assign y[7]=s[2] & s[1] & s[0]; 

endmodule 

OUTPUT: 

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/1fcd4e4a-b7c6-4bc8-bcd5-97084447681f)

                                                                                                       
MULTIPLEXER: 
 
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/bc769c01-236d-45b2-8322-e62a360a54ef)





PROGRAM:

module Mux_8_1(s0,s1,s2,i,y); 

input [7:0] i; 

input s0, s1, s2; 

output y; 

wire [7:0] w; 

assign w[0]=(~s2) & (~s1) & (~s0) & i[0]; 

assign w[1]=(~s2) &(~s1) &(s0) & i[1]; 

assign w[2]=(~s2) &(s1) &(~s0) & i[2]; 

assign w[3]=(~s2) &(s1) &(s0) & i[3]; 

assign w[4]=(s2) &(~s1) &(~s0) & i[4]; 

assign w[5]=(s2) &(~s1) &(s0) & i[5]; 

assign w[6]=(s2) &(s1) &(~s0) & i[6]; 

assign w[7]=(s2) &(s1) &(s0) & i[7]; 

assign y=w[0] |w[1] |w[2] |w[3] |w[4] |w[5] |w[6] |w[7]; 

endmodule 


OUTPUT:
 
![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/b22c70c9-8895-4066-9b2f-79fbe63f86ee)










DEMULTIPLEXER: 

 ![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/b3dab497-536c-4d2a-833c-2f306c8afc80)


PROGRAM: 

module Demux1_8(i, s0, s1, s2, y); 

input i; 

input s0, s1, s2; 

output [7:0] y; 

assign y[0]=~s0 &~s1 &~s2 & i; 

assign y[1]=~s0 &~s1 &s2 & i; 

assign y[2]=~s0 &s1 &~s2 & i; 

assign y[3]=~s0 &s1 &s2 & i; 

assign y[4]=s0 & ~s1 & ~s2 & i; 

assign y[5]=s0 & ~s1 & s2 & i; 

assign y[6]=s0 & s1 & ~s2 & i; 

assign y[7]=s0 & s1 &s2 & i; 

endmodule 


OUTPUT:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/dd959191-89c8-471f-9e16-6160aee02b94)

MAGNITUDE COMPARATOR:

![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/32ff0e16-6f6c-4c2d-8caa-25f6d0b9b248)

 




PROGRAM: 

module mag_cmp(a,b,l,g,e); 

input [3:0]a,b; 

output reg l,g,e; 

always @(*)

begin 

if(a>b) 

begin 

l=1'b0; 

g=1'b1; 

e=1'b0; 

end 

else if(a<b) 

begin 

l=1'b1; 

g=1'b0; 

e=1'b0; 

end 

else 

begin 

l=1'b0; 

g=1'b0; 

e=1'b1; 

end 

end 

endmodule 

OUTPUT:



![image](https://github.com/Karthikeyan8296/VLSI-EXP-2/assets/165583967/0025ee56-b8ad-41b8-b6d5-f6655672af5e)



RESULT: 

Thus, the combinational circuits of multiplexer, demultiplexer, encoder, decoder and magnitude comparator are implemented and simulated successfully.
