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
Step1: Define the specifications and initialize the design. 
Step2: Declare the name of the entity and architecture by using VHDL source code. 
Step3: Write the source code in VERILOG. 
Step4: Check the syntax and debug the errors if found, obtain the synthesis report. 
Step5: Verify the output by simulating the source code. 
Step6: Write all possible combinations of input using the test bench. 
Step7: Obtain the place and route report.  

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by: Harish R

RegisterNumber: 24001191
*/
```
module exp11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-21 020023](https://github.com/user-attachments/assets/4243ceca-5161-4518-8c6e-66c06ec3ad93)


**TIMING DIAGRAM FOR IP COUNTER**

![Screenshot 2024-12-21 020133](https://github.com/user-attachments/assets/cafff230-202b-4914-9d53-b5d1c18137c4)

**TRUTH TABLE**

![Screenshot 2024-12-21 021356](https://github.com/user-attachments/assets/ce23d0fe-6a01-4ed4-8bc7-9c2adbe15529)

**RESULTS**


Thus the Synchronous 3 bit Up counter is implemeted and verified.
