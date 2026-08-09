# CMOS D Latch Overview

A **D Latch** (Data or Delay Latch) is designed to solve the race condition and invalid state problem of the basic SR latch when both inputs are $1$. By using an **Enable ($E$)** input and a single **Data ($D$)** input, the latch ensures that the set and reset signals can never be active at the same time.

<img width="500" height="165" alt="image" src="https://github.com/user-attachments/assets/d06c9a23-8d0a-4153-8ef3-7e88915059cc" />


---

## How it Works
* When **Enable ($E$) = 0**: The latch is disabled (latched). It ignores any changes on the $D$ input and holds its current memory state ($Q$).
* When **Enable ($E$) = 1**: The latch is transparent. The output $Q$ follows the value of the $D$ input directly.

---

## Truth Table (D Latch)

| $E$ (Enable) | $D$ (Data) | $Q$ (Next State) | $\overline{Q}$ | Description |
| :---: | :---: | :---: | :---: | :--- |
| 0 | $X$ (Don't Care) | Previous $Q$ | Previous $\overline{Q}$ | **Hold / Latched State** |
| 1 | 0 | 0 | 1 | **Reset State** ($Q$ follows $D = 0$) |
| 1 | 1 | 1 | 0 | **Set State** ($Q$ follows $D = 1$) |

---

## Why the D Latch Solves the SR Latch Problem
In a standard SR latch, setting $S = 1$ and $R = 1$ at the same time creates an invalid, unpredictable race condition. 

The D latch fixes this by routing the single $D$ input through logic gates to the $S$ and $R$ inputs internally:
* If $D = 1$, then $S = 1$ and $R = 0$.
* If $D = 0$, then $S = 0$ and $R = 1$.

Because $S$ and $R$ are always exact opposites when the latch is enabled, **it is mathematically impossible to have $S = 1$ and $R = 1$ at the same time**, completely eliminating the invalid state and race conditions.
