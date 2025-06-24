# Digital FIR Filter Task 4 - CodTech Internship

This is my FIR filter project for codtech internship. I wrote Verilog code for a simple 4-tap FIR filter and created a testbench to test it.

## Filter Info

- 4-tap FIR filter (N=4)
- Coefficients used:
  - b0 = 1
  - b1 = 2
  - b2 = 3
  - b3 = 4
- It takes input signal `x_in` and gives output `y_out` using convolution.

## Files in this task

- `fir_filter.v` → design code of FIR filter
- `fir_tb.v` → testbench to simulate and check
- `fir.vcd` → waveform file generated after run
- eda playground link🔗

## How it works

- On every clock, new input sample is shifted into register array.
- Output is calculated like this:  
  `y_out = x[0]*b0 + x[1]*b1 + x[2]*b2 + x[3]*b3`

## Simulation Steps

I used `iverilog` and `gtkwave` to simulate and view waveform.

```bash
iverilog -o fir_test fir_filter.v fir_tb.v
vvp fir_test
gtkwave dump.vcd
