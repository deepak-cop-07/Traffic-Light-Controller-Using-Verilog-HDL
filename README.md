# Traffic-Light-Controller-Using-Verilog-HDL
## Aim
To design and simulate a traffic light controller using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 simulation environment. The objective is to control the traffic lights for a junction with a specific time-based sequence for Red, Yellow, and Green lights.

## Apparatus Required
Vivado 2023.1 or equivalent Verilog simulation tool.
Computer system with a suitable operating system.
FPGA board (optional for hardware verification).
Procedure
Launch Vivado 2023.1:

Open Vivado and create a new project.
Design the Traffic Light Controller Verilog Code:

Write the Verilog code for the traffic light controller, using an FSM (Finite State Machine) to transition between Green, Yellow, and Red lights based on timing intervals.
Create the Testbench:

Write a testbench to simulate the traffic light controller. The testbench will check the sequence of light transitions based on time.
Add the Verilog Files:

Add the traffic light controller Verilog code and the testbench file to the project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the correct sequence of the traffic lights.
Observe the Waveforms:

Examine the waveform output to verify that the traffic light transitions through the Green, Yellow, and Red lights in the correct sequence.
Save and Document Results:

Capture screenshots of the waveform and save the simulation logs to include in your report.

## Verilog Code for Traffic Light Controller
```
module traffic_light(clk,rst,light);
input clk, rst;
output reg [2:0]light;
parameter [1:0]s0=2'b00,
               s1=2'b01,
               s2=2'b10;
parameter [2:0]red=3'b001,
               yellow=3'b010,
               green=3'b100;
reg [1:0]state;
always@(posedge clk)
begin
      if(rst)begin
      light<=3'b0;
      state<=2'b0;
end
else
    case(state)
    s0:begin
            light<=green;
            state<=s1;
            end
     s1:begin
            light<=yellow;
            state<=s2;
            end
     s2:begin
            light<=red;
            state<=s0;
            end
 default:light=3'b0;
 endcase
 end
 endmodule
```

## output
![image](https://github.com/user-attachments/assets/de844d06-4951-4559-afc0-ae167e5dcc2f)

           









## Conclusion
In this experiment, a traffic light controller was successfully designed and simulated using Verilog HDL. The design controlled the traffic lights to switch between Green, Yellow, and Red in a cyclic manner based on timing intervals. The testbench verified that the traffic lights followed the correct sequence and timing. The simulation results confirm the correct functionality of the traffic light controller, demonstrating the effectiveness of Verilog HDL in designing FSM-based controllers for real-world applications.
