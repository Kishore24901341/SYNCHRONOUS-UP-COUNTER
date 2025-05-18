### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

Type the program in Quartus software.

Compile and run the program.

Generate the RTL schematic and save the logic diagram.

Create nodes for inputs and outputs to generate the timing diagram.

For different input combinations generate the timing diagram.

**PROGRAM**
```
 module ex11 (
    output reg [3:0] out,
    input clk,
    input rst
);
always @ (posedge clk) begin
    if (rst)
        out <= 4'b0000;
    else
        out <= out + 1;
end

endmodule
 
```
Developed by:KISHORE V RegisterNumber: 212224240077
*/

**RTL LOGIC UP COUNTER**

![image](https://github.com/user-attachments/assets/f14ff423-9d94-4a95-9f7f-f2d3c6432f9f)


**TIMING DIAGRAM FOR IP COUNTER**

![image](https://github.com/user-attachments/assets/55c30ffa-f012-4fab-92ab-6661bd7beadf)


**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/77d17e2e-b734-4a93-87a7-27decfa153b7)


**RESULTS**

Thus 4 bit synchronous up counter is implemented and functionality is validated.
