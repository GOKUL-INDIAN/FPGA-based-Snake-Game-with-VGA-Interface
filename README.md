# FPGA-based-Snake-Game-with-VGA-Interface
# 🐍 FPGA Snake Game (Verilog + VGA)

## 📌 Overview

This project implements a complete Snake Game in Verilog HDL, designed for FPGA and displayed via VGA (640x480 @ 60Hz).

The system integrates:

- VGA signal generation
- Finite State Machines (FSMs)
- LFSR-based random target generation
- Score and timer system
- Self-collision and boundary detection
- 7-segment display driver

---

## 🏗 System Architecture

### Major Modules

| Module | Function |
|--------|----------|
| Generic_counter | Reusable synchronous counter |
| Master_state_machine | Game state control (START, PLAY, WIN, LOSE) |
| Navigation_state_machine | Snake direction logic |
| VGA_module | VGA timing & pixel generation |
| Snake_control | Core game engine |
| random_num_gen | LFSR-based food generator |
| Score_counter | Score + timer + win/lose logic |
| decode_world | 7-segment display encoder |
| snake_wrapper | Top-level integration |

---

## 🎮 Game Features

- Snake movement using push buttons
- VGA 640x480 resolution output
- Target generation using LFSR
- Score win at 20 points
- Time-based lose condition (60 seconds)
- Self-collision detection
- Border collision detection
- Start / Play / Winner / Loser screens

---

## 🧠 FSM Design

### Master State Machine
- START
- PLAY
- WINNER
- LOSER

### Navigation State Machine
- UP
- DOWN
- LEFT
- RIGHT

---

## 🖥 VGA Details

- Resolution: 640x480 @ 60Hz
- Horizontal & Vertical sync generated using counters
- Pixel scaling for snake grid (160 x 120 logical resolution)

---

## 🏆 Win/Lose Logic

- Win → Score reaches 20
- Lose → 
  - Time exceeds 60 seconds (score < 10)
  - Self-collision
  - Boundary collision

---

## 🔢 Score Display

- 4-digit 7-segment display
- Multiplexed using strobe counter
- Active-low segment encoding

---

## 🛠 Tools Used

- Verilog HDL
- Xilinx Vivado
- FPGA Development Board (e.g., Basys 3 / Nexys)

---

## 📂 How to Run

1. Open Vivado
2. Create new RTL project
3. Add all files inside `/rtl`
4. Add constraints file
5. Set `snake_wrapper.v` as Top Module
6. Generate Bitstream
7. Program FPGA

---


  
