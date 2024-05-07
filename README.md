## SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM
 To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED
         Vivado 2023.2
         
## PROCEDURE
STEP:1 Start the Vivado, Select and Name the New project.

STEP:2 Select the device family, device, package and speed. 

STEP:3 Select new source in the New Project and select Verilog Module as the Source type. 

STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. 

STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. 

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. 

## LOGIC DIAGRAM
![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)

## PROGRAM
```
module FSM (clk,rst,x,z);
input clk,rst,x;
output z;
reg [2:1]Present_State,Next_State;
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;
always @(x,Present_State)
case(Present_State)
s0: if(x)
Next_State=s1;
else
Next_State=s0;
s1: if(x)
Next_State=s1;
else
Next_State=s2;
s2: if(x)
Next_State=s3;
else
Next_State=s0;
s3: if(x)
Next_State=s1;
else
Next_State=s0;
endcase
always@(negedge rst,posedge clk)
if(rst)
Present_State=s0;
else
Present_State<=Next_State;
assign z=(Present_State==s3);
endmodule
```

## OUTPUT:



## RESULT:



