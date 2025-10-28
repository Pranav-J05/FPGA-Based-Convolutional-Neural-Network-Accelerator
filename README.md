# FPGA-Based-Convolutional-Neural-Network-Accelerator



Overview
This project implements a simple Convolutional Neural Network (CNN) hardware accelerator on FPGA using Verilog. The accelerator includes core CNN operations:

3x3 Convolution layer

ReLU activation function

2x2 Max Pooling layer

It is designed and tested using Xilinx ISE, demonstrating image feature extraction in hardware.

Features
Modular and synthesizable Verilog design

RTL modules for convolution, ReLU, and max pooling

End-to-end top-level integration

Testbenches for functional verification

Designed for real-time CNN inference on FPGAs

Directory Structure:
conv3x3.v           # 3x3 convolution module  
relu.v              # ReLU activation module  
max_pool_2x2.v      # 2x2 max pooling module  
cnn_pipeline.v      # Top-level module integrating all components  
tb_cnn_pipeline.v   # Testbench for the integrated pipeline  


Getting Started
Prerequisites
Xilinx ISE (or compatible FPGA synthesis and simulation tools)

Basic understanding of Verilog HDL and digital design

Setup
Create a new project in Xilinx ISE targeting your FPGA device.

Add all Verilog files listed above to the project.

Set cnn_pipeline.v as the top-level module for synthesis and simulation.

Add tb_cnn_pipeline.v as the simulation top module to run behavioral simulations.

Running Simulation
Run behavioral simulation on tb_cnn_pipeline.v.

Verify that the pooled output matches expected results as printed in the simulation console.

Module Descriptions
conv3x3.v
Performs a 3x3 convolution on 8-bit pixel inputs and kernel weights over 9 clock cycles.

relu.v
Implements the ReLU activation function that outputs zero for negative inputs and passes positive inputs unchanged.

max_pool_2x2.v
Takes four 32-bit signed inputs and outputs the maximum value, implementing a 2x2 max pooling.

cnn_pipeline.v
Integrates convolution, ReLU, and max pooling into a sequential pipeline with control signals.
