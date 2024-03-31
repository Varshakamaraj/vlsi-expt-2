EXP.NO- 2
DATE-

AIM: To simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using VIVADO.

APPARATUS REQUIRED: VIVADO 2023.2

PROCEDURE:
 STEP:1 Start the Vivado, Select and Name the New project.
 STEP:2 Select the device family, device, package and speed. 
STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.
 STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

      ENCODER 8:3:
![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/8be107ac-a9f3-46c5-8335-d9517dbfb980)

PROGRAM:

module encoder(i, a, b, c);
input [7:0]i;
output a,b,c;
assign a=i[4] | i[5] | i[6] | i[7]; 
assign b=i[2] | i[3] | i[6] | i[7]; 
assign c=i[1] | i[3] | i[5] | i[7];
endmodule

                      OUTPUT:       
                      ![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/f60f555b-4a1a-4936-89de-243fd634188e)

                    DECODER3:8:
                    ![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/e8c3fe67-a738-48c7-ac97-e04af5a81a50)



PROGRAM:
module decoder_3_8(s,y);
input [2:0]s;
output [7:0]y;
assign y[0]=~s[2]&~s[1]&~s[0];
assign y[1]=~s[2]&~s[1]&s[0];
assign y[2]=~s[2]&s[1]&~s[0];
assign y[3]=~s[2]&s[1]&s[0];
assign y[4]=s[2]&~s[1]&~s[0];
assign y[5]=s[2]&~s[1]&s[0];
assign y[6]=s[2]&s[1]&~s[0];
assign y[7]=s[2]&s[1]&s[0];
endmodule


OUTPUT:
 
![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/5c2a78b8-b9ac-460f-ac83-d8774df08ea5)

                
MULTIPLEXER 8:1:

![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/bbf8ef21-c988-45d7-a98c-ff5d984e0554)

PROGRAM: 
module Mux 8 1 (s0,s1,s2, i,y);
input [7:0]i;
input 50, s1,s2;
output y;
wire [7:0]w;
assign w[0]=(~s2) & (~sl) & (~50)&i[0];


assign w[1]=(~32)&(~51) & (50) &i [1];
assign w[2]=(~52) & (sl) & (~50)&i [2];
assign w[3]=(~52) & (51) & (50) &i [3];
assign w[4]=(s2) & (sl) & (~50)&i [4];
assign w[5]=(s2) & (sl) & (s0) &i [5];
assign w[6]=(52) & (51)&(~50)&i [6];
assign w[7]=(s2) & (51) & (s0)&i [7];
assign y=w[0][w[1] w[2] w[3] w[4] w[5] w[6] w[7];
endmodule

OUTPUT:

![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/13ded9fd-773a-43ea-a0bc-ec2ebe539d32)



                       DEMULTIPLEXER 1:8:
                       ![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/53691013-4bab-479d-98e8-434c8c44ddb9)


PROGRAM:
module fa (a,b,c,sum, carry);
input a,b,c;
output sum, carry;
wire w1,w2,w3;
xor gl(wl,a,b);
xor g2 (w2,a,b);
xor g3 (sum, w1,c);
and (w3,c,w1);
or g5 (carry, w3,w2);
endmodule
OUTPUT:
![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/4d66b95f-0bca-4b41-b5e8-32c0b617e2d8)


                       COMPARATOR:
                       ![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/9e1eb3ed-74e6-4ced-acac-d4678e6dfd66)

 
PROGRAM:
module comparator(a,b,l,g,e);
input [3:0]a,b;
output reg l,g,e;
always@(*)
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
![image](https://github.com/Varshakamaraj/vlsi-expt-2/assets/165577098/eea5f481-701c-4a63-bb2f-5d5e767a47b5)


RESULT:
	The simulate and synthesis ENCODER, DECODER, MULTIPLEXER, DEMULTIPLEXER, MAGNITUDE COMPARATOR using VIVADO is successfully verified.

