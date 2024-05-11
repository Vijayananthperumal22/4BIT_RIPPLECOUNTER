# 4BIT_RIPPLECOUNTER
# Circuit Diagram
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/324dfe68-4985-401a-9f0c-7df90b08265e)
# T- Flip Flop
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/2c234c0e-2c48-4688-920b-a43ea6582112)
# D - Flip flop
![image](https://github.com/RESMIRNAIR/4BIT_RIPPLECOUNTER/assets/154305926/7fb0da71-700b-4a53-b2c1-2afa523e89c4)

# PROGRAM
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
# OUTPUT 
![image](https://github.com/Vijayananthperumal22/4BIT_RIPPLECOUNTER/assets/107705127/88da3bd5-6ec1-4401-8133-22ef80f8b90f)
