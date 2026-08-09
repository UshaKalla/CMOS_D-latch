# SR Latch 
- the most fundamental circuit that introduces memory 
____
<img width="422" height="307" alt="image" src="https://github.com/user-attachments/assets/7737ea28-95f7-4ff2-940d-476496536c73" />

# SR Latch Overview & Truth Table

An **SR Latch** (Set-Reset Latch) is built by cross-coupling two logic gates—either **NOR gates** or **NAND gates**.

* **Cross-coupling** occurs when the output of one gate is wired to the input of another gate. 
* This creates a feedback loop that ensures the circuit can lock (or "remember") states even after you stop pressing the button.

An SR Latch has **2 inputs** ($S$ for Set and $R$ for Reset) and **2 outputs** ($Q$ and $\overline{Q}$, known as Q-not).

---

## Why $\overline{Q}$ is Necessary
$\overline{Q}$ is necessary to complete the feedback loop and provide the complementary (inverted) state of the output, maintaining the stable toggle mechanism of the latch.

---

## Truth Table (NOR-based SR Latch)

| $S$ (Set) | $R$ (Reset) | $Q$ | $\overline{Q}$ | State Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | 0 |  Previous $Q$  |  Previous $\overline{Q}$  | **Memory / Hold State** (remembers last state) |
| 0 | 1 | 0 | 1 | **Reset** (forces $Q = 0$) |
| 1 | 0 | 1 | 0 | **Set** (forces $Q = 1$) |
| 1 | 1 | 0 | 0 | **Invalid / Forbidden State** |

---

## The $S=1, R=1$ Problem
Setting both $S = 1$ and $R = 1$ simultaneously is equivalent to wanting to turn a switch **ON** and **OFF** at the exact same time. 

This causes a race condition where the gates compete to determine whether $Q$ or $\overline{Q}$ will be $1$. Because this outcome is entirely random and unpredictable, this state is considered invalid and should be avoided in digital design.
