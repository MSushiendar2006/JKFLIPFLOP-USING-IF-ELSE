# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
```
1.Setup: Open Quartus Prime software and create a new project. Name the project and add a new Verilog file for coding the JK flip-flop.

2.Coding: Write the Verilog code for the JK flip-flop using if-else and case statements to control the flip-flop’s behavior based on the inputs J, K, clk, and rst. Ensure the logic includes cases for hold, reset, set, and toggle operations.

3.Compile: Save and compile the code to check for syntax errors. Ensure that the program runs without errors to confirm the code is syntactically correct.

4.Simulation Setup: Set up a testbench for the JK flip-flop to simulate its behavior. Apply various test inputs according to the functional table of the JK flip-flop to observe and validate output behavior.

5.Observe Outputs: Run the simulation and observe the timing diagram to confirm the correctness of the JK flip-flop’s functionality for each possible input combination.
```

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
Developed by: Sushiendar M
RegisterNumber: 212223040217
*/
```
module jkflipflop(j, k, clk, rst,q);
input j, k, clk, rst;
output reg q;
initial
begin
q=1'b1;
end


always @(posedge clk or posedge rst) 
begin
    if (rst) 
        q <= 0;          // Reset the flip-flop
    else begin
        case ({j, k})    // J and K control the behavior
            2'b00: q <= q;       // No change
            2'b01: q <= 0;       // Reset
            2'b10: q <= 1;       // Set
            2'b11: q <= ~q;      // Toggle
        endcase
    end
end

endmodule
```

**RTL LOGIC FOR FLIPFLOPS**
![image](https://github.com/user-attachments/assets/50f43d8d-d0aa-40f8-8c64-44d579ea4c85)


**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/user-attachments/assets/178a3bfe-05bb-4a49-af64-f4f1dd622853)





**RESULTS**
The JK flip-flop was successfully implemented in Verilog, and its functionality was validated according to the functional tables.
