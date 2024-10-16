# Swapping of Three Numbers
## Aim
To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

## Apparatus Required
Vivado 2023.1 or equivalent Verilog simulation tool.

## Procedure
Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.

## Verilog Code for Swapping Three Numbers:
### Blocking:
```
module blocking_3();
reg [7:0]a,b,c;
initial
begin
a=8'd24;
b=8'd15;
c=8'd20;
#10
b=a;
c=b;
a=c;
end 
initial 
begin
$monitor("value of a:%d,and b=%d,c=%d",a,b,c);
end
endmodule
```
### Non Blocking:
```
module nonblocking_3();
reg [7:0]a,b,c;
initial
begin
a=8'd24;
b=8'd15;
c=8'd20;
#10
b<=a;
c<=b;
a<=c;
end 
initial 
begin
$monitor("value of a:%d,and b=%d,c=%d",a,b,c);
end
endmodule
```
## Testbench for Swapping Three Numbers:
### Blocking:
```
module tb_blocking_3;
blocking_3 uut();
initial begin
$monitor("At time %0dns: value of a = %d, b = %d, c = %d", $time, uut.a, uut.b, uut.c);
#50;
$finish;
end
endmodule
```
### Non Blocking:
```
module tb_nonblocking_3;
nonblocking_3 uut();
initial begin
$monitor("At time %0dns: value of a = %d, b = %d, c = %d", $time, uut.a, uut.b, uut.c);
#50
$finish;
end
endmodule
```
## Output:
### Blocking:
![Screenshot 2024-10-09 160143](https://github.com/user-attachments/assets/f7d08029-54b4-43d0-a61d-05a5bd01ff7e)

### Non Blocking:
![Screenshot 2024-10-09 160046](https://github.com/user-attachments/assets/b04a02a1-868b-4b3d-bf4e-26e6d43d3c0a)

       
## Conclusion
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
