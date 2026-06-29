# 📟 Texas Instruments TI-59C Web Simulator

A premium, high-fidelity web-based emulator of the legendary **Texas Instruments TI-59** programmable calculator. This simulator faithfully reproduces the iconic look, weight, and feel of the original hardware—including its premium golden-register layout—while driving a precise mathematical processing engine beneath the hood.

Developed as an open, modular academic research project, this emulator serves both as an educational tool and a nostalgic tribute to early programmable computing.

---

## 🚀 Live Demo & Project Info

[![Launch on GitHub Pages](https://shields.io)](https://web.app)
[![License: MIT](https://shields.io)](https://opensource.org)

* **Project Status:** Academic Research & Development
* **Simulator Version:** 1.0.4 (Stable Math Build)

---

## 🛠️ Tech Stack

This project is engineered entirely on the frontend for maximum portability, sub-millisecond rendering, and zero server overhead:

* **Core Structure:** Semantic HTML5
* **Styling & Theme Engine:** Modern CSS3 featuring dynamic Custom Properties (`:root`) for pixel-perfect retro aesthetics and full responsiveness.
* **Computation & Logic Core:** Pure Vanilla JavaScript (ES6+) utilizing high-precision linear registers and processing stacks.

---

## 📖 User Manual & Documentation

<details>
<summary><b>1. Introduction & Architectural Limitations (Turing Completeness)</b></summary>

### ⚠️ Critical Architectural Note
From a theoretical computer science perspective, this emulator is **not a Turing-complete machine**. The current coprocessor implementation supports exclusively **linear program execution**.

* **What is excluded:** Conditional branching (e.g., <kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">x=t</kbd>), unconditional jumps (<kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">GTO</kbd>), loops, and indirect addressing are intentionally left out of this academic release.
* **Extensibility:** The project is designed as an open, modular system. Developers are welcome to clone the repository and implement the missing instruction sets locally.

</details>

<details open>
<summary><b>2. Implemented Core Functions Spec (Command List)</b></summary>

The following core calculation and utility modules are fully operational in this stable build:

| Functional Module | Description | Activation Keys |
| :--- | :--- | :--- |
| **Calculation Chains** | Seamlessly evaluates long arithmetic strings (e.g., `2 + 3 * 4`), processing intermediate results without dropping the stack. | <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">ADD</kbd> <kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">SUB</kbd> <kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">MUL</kbd> <kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">DIV</kbd> |
| **2nd Prefix Register** | Shifts the keyboard mapping to execute the premium "golden" commands printed above the physical keys. | <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd> |
| **Direct Memory Addressing** | Features a dedicated array of 100 general-purpose registers (`R00`–`R99`). Requires entering a two-digit cell address. | <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">STO</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">RCL</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">SUM</kbd> + `[0-9][0-9]` |
| **Angular Conversion** | Handles precise angular conversions between radians and degrees based on the system's current trigonometric mode. | <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd> ➔ <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">CE</kbd> (deg) / <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">CLR</kbd> (rad) |
| **Math Functions** | Advanced computation including square roots, squaring, natural/base-10 logarithms, exponents, trigonometry, and inverse trig. | <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">SQRT</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">X2</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">sin</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">cos</kbd> <br> <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd> + <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">INVX</kbd> (`|x|`) |
| **Linear Coprocessor** | Records key opcodes into a 960-step program array for automated sequential playback. | <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">LRN</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">SST</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">BST</kbd> <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">RST</kbd> <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">R_S</kbd> |

</details>

<details>
<summary><b>3. Test Cases: Arithmetic Mode</b></summary>

### Test #1: Absolute Value of a Negative Number (`|x|`)
*Objective: Verify the prefix-register shifting logic and sign inversion.*

1. Input the number <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">1</kbd>.
2. Press <kbd style="background:#333; color:#fff; border:1px solid #555; padding:2px 6px; border-radius:3px;">+/−</kbd> (or `SIGN`) ➔ *The display will show `-1.`*.
3. Press the golden prefix key <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd>.
4. Press the <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">1/x</kbd> key (which invokes the <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">|x|</kbd> module).
5. **Expected Result:** `1.` (The negative sign is successfully stripped).

### Test #2: Radians to Degrees Conversion (`rad` ➔ `deg`)
*Objective: Verify system constant extraction ($\pi$) and angular transforms.*

1. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">CLR</kbd> to perform a complete system register reset.
2. Flip the physical toggle switch at the top of the screen to **RAD** mode.
3. Press <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd>, then press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">3</kbd> to recall the built-in constant <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">pi</kbd> ➔ *The display will read `3.141592654`*.
4. Press <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">2nd</kbd>, then press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">CE</kbd> to trigger the <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">deg</kbd> command.
5. **Expected Result:** `180.` (Radians are correctly converted into degrees).

</details>

<details>
<summary><b>4. Test Cases: Program Mode (LRN) & Memory Constraints</b></summary>

### ⚠️ Internal Program Constraint: Numbers with Zeros
Due to how key opcodes are stored sequentially, **manually typing numbers that contain zeros (e.g., hardcoding the constant `10`) inside the `LRN` programming mode will cause execution glitches or register skipping.**

* **The Solution:** Any constants containing zeros must be pre-loaded into general-purpose memory registers (`R00`–`R99`) in standard calculation mode **BEFORE** writing or running your program. Inside the `LRN` sequence, simply call that register using the `RCL` command.

---

### Code Blueprint: Calculating $f(x) = x^2 + 10$

#### Step A: Pre-loading the constant into Memory
1. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">CLR</kbd> to wipe the interface.
2. Type the target constant: <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">1</kbd> ➔ <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">0</kbd>.
3. Save it to register five by pressing <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">STO</kbd>, followed by the two-digit address <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">0</kbd> ➔ <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">5</kbd>.

#### Step B: Recording the Linear Sequence
1. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">RST</kbd> to reset the program counter to zero.
2. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">LRN</kbd> to enter Teach/Learn mode ➔ *The display switches to the step format `000 00`*.
3. Key in the following strict instruction sequence:
   * <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">X2</kbd> *(Squares the variable currently on the screen)*
   * <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">ADD</kbd> *(Initiates addition)*
   * <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">RCL</kbd> ➔ <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">0</kbd> ➔ <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">5</kbd> *(Safely recalls the constant '10' from register 05)*
   * <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">ADD</kbd> *(Closes and evaluates the current operation)*
   * <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">R_S</kbd> *(Run/Stop command to halt execution and output the final result)*
4. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">LRN</kbd> again to exit programming mode.

#### Step C: Automated Execution
1. Press <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px; box-shadow: 1px 1px 0px #ccc;">RST</kbd> to snap the program pointer back to step zero.
2. Enter your test argument, for example: <kbd style="background:#fff; color:#333; border:1px solid #ccc; padding:2px 6px; border-radius:3px;">5</kbd>.
3. Press <kbd style="background:#ffcc00; color:#000; font-weight:bold; border:1px solid #cca300; padding:2px 6px; border-radius:3px;">R_S</kbd> to trigger the linear coprocessor.
4. **Expected Result:** `35.` (The formula executes perfectly).

</details>

---

## 📝 License

Distributed under the MIT License. See `LICENSE` for more information.
