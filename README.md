# test-1
I have created my first Verilog HDL program on Multiplexer on Xilinx Vivado.

/verilog code
module mux(in,sel,out);
input[15:0] in;
input[3:0] sel;
output out;
assign out=in[sel];
endmodule

/testbench code
module mux_tb();
reg[15:0] A;reg[3:0]S; wire F;
mux M(.in(A),.sel(S),.out(F));
initial
begin
$dumpfile("mux.vcd");
$dumpvars(0,mux_tb);
$monitor($time,"A=%h,S=%h,F=%b",A,S,F);
#5 A=16'h3f0a;
#5 S=4'h1;
#5 S=4'hb;
#5 S=4'hc;
#5 $finish;
end


endmodule
