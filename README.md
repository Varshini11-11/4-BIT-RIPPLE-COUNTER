# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

/* write all the steps invloved */
/* 1.Increment count on each positive edge of the clock. 
2.Reset count to zero when it reaches 15. 
3.Generate clock signal (clk). 
4.Instantiate the RippleCounter module.
5.Conduct fuctional testing by displaying the count at each clock cycle for 16 cycles */

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
```
module ripple_counter_4bit (
    input wire clk,        // Clock input
    input wire reset,      // Asynchronous reset (active high)
    output reg [3:0] count // 4-bit output count
);

    // Internal signals for flip-flop clocks
    wire tff0_clk;
    wire tff1_clk;
    wire tff2_clk;
    wire tff3_clk;

    assign tff0_clk = clk;
    assign tff1_clk = count[0];
    assign tff2_clk = count[1];
    assign tff3_clk = count[2];

    // Flip-flop for bit 0 (LSB)
    always @(posedge tff0_clk or posedge reset) begin
        if (reset)
            count[0] <= 0;
        else
            count[0] <= ~count[0];
    end

    // Flip-flop for bit 1
    always @(posedge tff1_clk or posedge reset) begin
        if (reset)
            count[1] <= 0;
        else
            count[1] <= ~count[1];
    end

    // Flip-flop for bit 2
    always @(posedge tff2_clk or posedge reset) begin
        if (reset)
            count[2] <= 0;
        else
            count[2] <= ~count[2];
    end

    // Flip-flop for bit 3 (MSB)
    always @(posedge tff3_clk or posedge reset) begin
        if (reset)
            count[3] <= 0;
        else
            count[3] <= ~count[3];
    end

endmodule
```

 Developed by:varshini G RegisterNumber:212224050056
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/7f55b2b2-a305-4e47-939f-09668369d26f)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/9d64bd74-2cf0-473e-afee-22d0f679061d)

**RESULTS**
Thus the program to implement a 4 Bit Ripple Counter using verilog and validating their functionality using their functional tables is successfully completed.
