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

## Verilog Code:
```
module normal_code(a,b,c,x,y,z);
    input[3:0]a; 
    input[3:0]b;
    input[3:0]c;
    output reg [3:0]x; 
    output reg [3:0]y; 
    output reg [3:0]z;

    always @(*) begin
        x <= c;
        y <= a;
        z <= b;
    end
endmodule
```
## Testbench for Swapping Three Numbers:
```
module normal_tb;
    reg [3:0] a, b, c;
    wire [3:0] x, y, z;

    // Instantiate swap_three module
    normal_code dut(
        .a(a), 
        .b(b), 
        .c(c), 
        .x(x), 
        .y(y), 
        .z(z)
    );

    initial begin
        // Test case 1: Positive numbers
        a = 4'd6;
        b = 4'd5;
        c = 4'd4;
        #10;


        // Test case 3: Mixed numbers
        a = 4'd3;
        b = 4'd2;
        c = 4'd1;
        #10;

        $finish;
    end
    
       // Monitor outputs
    initial begin
        $monitor("Time = %0t, a = %0d, b = %0d, c = %0d, x = %0d, y = %0d, z = %0d",
                 $time, a, b, c, x, y, z);
    end
endmodule
```
## sample output
![Screenshot 2024-10-09 154722](https://github.com/user-attachments/assets/7a5029a9-dd44-4471-bb94-234ecc696820)

       
## Conclusion
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.
