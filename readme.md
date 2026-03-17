# 32-bit Arithmetic Logic Unit (ALU) for the Beta Processor

In this lab, we will build a 32-bit **Arithmetic and Logic Unit (ALU)** for the Beta processor. This ALU will be essential for your 1D Project Checkoff 1 and Lab 4, where we’ll expand on it to build a complete Beta CPU.

## Overview

The **Arithmetic Logic Unit (ALU)** is a **combinational logic device** responsible for performing arithmetic and logic operations within a CPU. Our ALU has two 32-bit inputs (`A` and `B`) and produces a 35-bit output:
- `alu[31:0]`: The primary 32-bit result of the operation.
- `Z`: Zero flag, indicating if the result is zero.
- `V`: Overflow flag.
- `N`: Negative flag.

## ALU Modules

To build the ALU modularly, we will create separate units for each core operation. These include:
1. **Addition/Subtraction Unit** - Handles basic addition and subtraction.
2. **Comparison Unit** - Used for branching by comparing values.
3. **Boolean Unit** - Performs bitwise operations like XOR and masking.
4. **Shifter Unit** - Supports bit shifts for division/multiplication by 2 and data manipulation.
5. **Multiplier Unit** - Responsible for multiplication, requiring a more complex design.

Each of these modules will generate its own 32-bit output, which we’ll later combine to produce a single ALU result.

Consult 50.002 lab handout for more information.

# How to use

Toggle between manual and auto tester using `io_dip[2][6]`. `0`: Auto, `1`: Manual.

## Manual Tester

- Use `io_dip[1:0]` to set inputs for the ALU
- Use `io_dip[2][5:0]` to set opcode for the ALU
- Press `io_button[0]` to confirm input & transit to the next state of the FSM
- `io_led[2][7:5]` displays current FSM state

States:
- `000` `SET_A_LOW`: set input a[15:0]
- `001` `SET_A_HIGH`: set input a[31:16]
- `010` `SET_B_LOW`: set input b[15:0]
- `011` `SET_B_HIGH`: set input b[31:16]
- `100` `DISPLAY_OUT`: `io_led[1:0]` displays lower 16 bits of ALU's output (default), `io_led[2][2:0]` displays ZVN values -- `Z`: `io_led[2][2]`, `V`: `io_led[2][1]`, `N`: `io_led[2][0]`.

- Hold `io_button[1]` to display higher 16 bits of ALU's output.

## Auto Tester

- Press `io_button[0]` to start auto tester.
- `io_dip[2][7]`: Force error
  
LED:
- `led[5:0]`: state debug
- `led[6]`: Running
- `led[7]`: Error
  
IO_LED:
- `io_led[0]`: Test case index
- `io_led[1]`: ALU output, displays first 8 bits of ALU's output by default
- `io_led[2]`: Expected output, displays first 8 bits of expected output by default

- Hold `io_button[3]` to display second 8 bits
- Hold `io_button[1]` to display third 8 bits
- Hold `io_button[4]` to display last 8 bits
