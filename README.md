# HDL_EXP3
# 4BIT_SYNCHRONOUS_UP_COUNTER
# AIM:
To stimulate and synthesis 4bit synchronous upcounter using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

![image](https://github.com/RESMIRNAIR/4BIT_SYNCHRONOUS_UP_COUNTER/assets/154305926/4d676d34-2f12-420a-9c55-befa279f5ec0)

# Truth Table

 <img width="362" alt="image" src="https://github.com/RESMIRNAIR/4BIT_SYNCHRONOUS_UP_COUNTER/assets/154305926/2be84c5a-099f-4418-8d0b-ace34f734342">
 
# Timing diagram of the synchronous counter

![image](https://github.com/RESMIRNAIR/4BIT_SYNCHRONOUS_UP_COUNTER/assets/154305926/62c47758-b0a4-4fe0-842f-5c4245a88ff2)

# Program:
    module synchronous_up_counter(
    input wire clk, 
    input wire reset, 
    output reg [3:0] count // 4-bit output );
    always @(posedge clk or posedge reset)
    begin
    if (reset)
    count <= 4'b0000;
    else
    count <= count + 1; 
    end
    endmodule

# Output:

![323154878-d946353a-c8bb-4ac0-8ef5-254f2890e09b](https://github.com/durgareddy654/4BIT_SYNCHRONOUS_UP_COUNTER/assets/161814262/f2f7163f-2cf0-4f2d-84c9-e42e448fb673)

# Result:
Thus the verilog program for 4bit synchronous upcounter has been simulated and verified successfully.


# 8BIT_SYNCHRONOUS_UP-DOWN_COUNTER
# Aim:
To stimulate and synthesis 4bit Ripple counter using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/e1af47bf-e77f-446e-9fe0-e0ca3d1a7cfd)

# Here is a diagram showing the circuit in the "up" counting mode

![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/8a6dd34b-5226-4d93-9bff-d87ab85aeabc)

# Here, shown in the "down" counting mode

![image](https://github.com/RESMIRNAIR/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/154305926/9a30ebd6-6692-48d0-b64b-41b896d6de4a)

# Program
    module ripple_carry_counter(q, clk, reset);
    output [3:0] q;
    input clk, reset;
    T_FF tff0(q[0], clk, reset);
    T_FF tff1(q[1], q[0], reset);
    T_FF tff2(q[2], q[1], reset);
    T_FF tff3(q[3], q[2], reset);
    endmodule
    module T_FF(q, clk, reset);
    output q;
    input clk, reset;
    wire d;
    D_FF dff0(q, d, clk, reset);
    not n1(d, q);
    endmodule
    module D_FF(q, d, clk, reset);
    output q;
    input d, clk, reset;
    reg q;
    always @(posedge reset or negedge clk)
    if (reset)
    q = 1'b0;
    else
    q = d;
    endmodule

# Output

![image](https://github.com/trishasailendran/8BIT_SYNCHRONOUS_UP-DOWN_COUNTER/assets/87655678/ffd75f6f-e811-4f25-a519-270954a27e57)

# Result
Thus the verilog program for 4bit Ripple Counter has been simulated and verified successfully.


# 4BIT_RIPPLECOUNTER
# Aim:
To stimulate and synthesis 4bit Ripple counter using Vivado.

# Software Required:
vivado 2023.2 software.

# Procedure:
STEP:1 Start the vivado software, Select and Name the New project.

STEP:2 Select the device family, device, package and speed.

STEP:3 Select new source in the New Project and select Verilog Module as the Source type.

STEP:4 Type the File Name and module name and Click Next and then finish button. Type the code and save it.

STEP:5 Select the run simulation and then run Behavioral Simulation in the Source Window and click the check syntax.

STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.

STEP:7 compare the output with truth table.

# Circuit Diagram

![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/324dfe68-4985-401a-9f0c-7df90b08265e)

# T- Flip Flop

![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/2c234c0e-2c48-4688-920b-a43ea6582112)

# D - Flip flop

![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/7fb0da71-700b-4a53-b2c1-2afa523e89c4)

# Program:

```
module ripple_carry_counter(q, clk, reset);
output [3:0] q;
input clk, reset;
T_FF tff0(q[0], clk, reset);
T_FF tff1(q[1], q[0], reset);
T_FF tff2(q[2], q[1], reset);
T_FF tff3(q[3], q[2], reset);
endmodule
module T_FF(q, clk, reset);
output q;
input clk, reset;
wire d;
D_FF dff0(q, d, clk, reset);
not n1(d, q);
endmodule
module D_FF(q, d, clk, reset);
output q;
input d, clk, reset;
reg q;
always @(posedge reset or negedge clk)
if (reset)
q = 1'b0;
else
q = d;
endmodule
```

# Output:

![image](https://github.com/trishasailendran/4BIT_RIPPLECOUNTER/assets/87655678/cfda3369-85d9-4655-83a8-3c4f864d3b5b)

# Result:
Thus the verilog program for 4bit Ripple Counter has been simulated and verified successfully.
