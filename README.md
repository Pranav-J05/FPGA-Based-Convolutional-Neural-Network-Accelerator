# FPGA-Based-Convolutional-Neural-Network-Accelerator


Absolutely! Here’s an **enhanced and more professional version** of your GitHub README — formatted cleanly, visually structured, and more engaging for readers. It uses proper Markdown styling, headings, emojis, and concise yet impactful phrasing 👇

---

# ⚙️ FPGA-Based Convolutional Neural Network (CNN) Accelerator

### 🚀 Overview

This project implements a **hardware-accelerated Convolutional Neural Network (CNN)** on an **FPGA** using **Verilog HDL**.
It demonstrates real-time **image feature extraction** using three fundamental CNN operations — **Convolution**, **ReLU activation**, and **Max Pooling** — all realized in synthesizable RTL.

### 🧠 Core Features

* 🧩 **Modular Verilog Design** – Clean, parameterized modules for each CNN operation
* 🔁 **Pipeline Integration** – End-to-end data flow through convolution, activation, and pooling
* ⚡ **Synthesizable RTL** – Verified for FPGA implementation using Xilinx ISE
* 🧪 **Functional Testbenches** – Behavioral simulation and validation of CNN output
* 🖼️ **Hardware Image Processing** – Demonstrates real-time CNN inference on FPGA hardware

---

### 🏗️ Architecture Overview

The accelerator performs CNN computation in three key stages:

| Stage               | Module           | Description                                                                           |
| ------------------- | ---------------- | ------------------------------------------------------------------------------------- |
| **1️⃣ Convolution** | `conv3x3.v`      | Performs 3×3 convolution on 8-bit pixel inputs and kernel weights over 9 clock cycles |
| **2️⃣ Activation**  | `relu.v`         | Applies ReLU: outputs 0 for negatives, passes positives unchanged                     |
| **3️⃣ Pooling**     | `max_pool_2x2.v` | Executes 2×2 max pooling to reduce feature map size                                   |

All modules are integrated in `cnn_pipeline.v` to form the complete CNN data path.

---

### 📂 Directory Structure

```
FPGA-Based-CNN-Accelerator/
│
├── conv3x3.v          # 3x3 Convolution module
├── relu.v             # ReLU activation module
├── max_pool_2x2.v     # 2x2 Max pooling module
├── cnn_pipeline.v     # Top-level CNN pipeline integration
├── tb_cnn_pipeline.v  # Testbench for full CNN pipeline
└── README.md          # Project documentation
```

---

### 🧰 Getting Started

#### 🖥️ Prerequisites

* **Xilinx ISE** (or compatible FPGA toolchain)
* Basic understanding of **Verilog HDL** and **digital system design**

#### ⚙️ Setup Instructions

1. Create a new project in **Xilinx ISE** targeting your FPGA board.
2. Add all Verilog source files listed above.
3. Set **`cnn_pipeline.v`** as the *top-level module* for synthesis.
4. Set **`tb_cnn_pipeline.v`** as the *simulation top module*.

---

### ▶️ Running Simulation

1. Run **behavioral simulation** on `tb_cnn_pipeline.v`.
2. Observe the **output feature map** in the simulation console.
3. Verify that the **pooled output** matches expected CNN results.

---

### 🧩 Module Highlights

#### 🟢 `conv3x3.v`

* Performs **3×3 convolution** on 8-bit pixel inputs.
* Operates over **9 clock cycles** per convolution window.

#### 🟣 `relu.v`

* Implements **ReLU activation**:
  [
  f(x) = \begin{cases}
  0, & x < 0 \
  x, & x \geq 0
  \end{cases}
  ]

#### 🔵 `max_pool_2x2.v`

* Applies **2×2 max pooling** for dimensionality reduction and feature enhancement.

---

### 🧾 Future Enhancements

* Add **parameterized kernel sizes** (e.g., 5×5)
* Integrate **multiple convolution layers**
* Support for **multi-channel inputs (RGB)**
* Implement **fixed-point quantization** for improved FPGA efficiency

---

### 🏁 Conclusion

This project showcases how **CNN inference can be achieved in hardware**, bridging the gap between **AI algorithms and FPGA-based digital systems**.
It serves as a strong foundation for further research and development in **hardware-accelerated machine learning**.

---






max_pool_2x2.v
Takes four 32-bit signed inputs and outputs the maximum value, implementing a 2x2 max pooling.

cnn_pipeline.v
Integrates convolution, ReLU, and max pooling into a sequential pipeline with control signals.
