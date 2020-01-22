## Quick reference
- [1. Present the given number in the NKB, BCD, U1, U2 codes as positive and negative value](#1)

- [2. Present the given number in hexadecimal code](#2)

- [3. Present the given number as negative in the 2'complement](#3)

- [4. Perform simple calculations for two numbers in the 1'complement](#4)

- [5. Perform simple calculations for two numbers in the 2'complement](#5)

- [6. Multiplication of two binary numbers](#6)

- [7. Adding two numbers in the BCD and EXCESS-3 code](#7)

- [8. Negating numbers in the BCD and EXCESS-3 code](#8)

- [9. Describe the AND, OR and XOR gates](#9)

- [10. Describe the XNOR, NAND and NOR gates](#10)

- [11. Present a circuit built of gates that will perform a specific function (depending on the appropriate combination of input data)](#11)

- [12. Describe the adder adding two bits, present its diagram](#12)

- [13. Present a scheme of size comparator that comparing two binary values (equality, and which of them is larger) and describe comparators](#13)

- [14. Draw a symbol, diagram with gates and describe how the SR latch works](#14)

- [15. Describe the SR flip-flop](#15)

- [16. Describe the D flip-flop and T flip-flop](#16)

- [17. Describe the multiplexer and demultiplexer](#17)

- [18. Present a Karnaugh map for a given function, minimize it, write canonical normal forms (product and summative) forms of a function after minimizing it, draw a diagram](#18)

- [19. Describe static-hazards](#19)

# <a name="1"></a>1. Present the given number in the NKB, BCD, U1, U2 codes as positive and negative value
---

# <a name="2"></a>2. Present the given number in hexadecimal code
---

# <a name="3"></a>3. Present the given number as negative in the 2'complement
---

# <a name="4"></a>4. Perform simple calculations for two numbers in the 1'complement
---

# <a name="5"></a>5. Perform simple calculations for two numbers in the 2'complement
---

# <a name="6"></a>6. Multiplication of two binary numbers
---

# <a name="7"></a>7. Adding two numbers in the BCD and EXCESS-3 code
---

# <a name="8"></a>8. Negating numbers in the BCD and EXCESS-3 code

---

# <a name="9"></a>9. Describe the AND, OR and XOR gates
### AND gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/AND_ANSI_Labelled.svg/120px-AND_ANSI_Labelled.svg.png)

Implements logical conjunction. With inputs A and B and output C implements the logical expression C = A · B. Finds the minimum between two binary digits. C-like languages use the symbol & to denote bitwise AND.

 A | B | Q
 - | - | -
 0 | 0 | 0
 0 | 1 | 0
 1 | 0 | 0
 1 | 1 | 1

If no specific AND gates are available, one can be made from NAND or NOR gates shown in the image below.

NAND construction | NOR construction
- | -
![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/AND_from_NAND.svg/200px-AND_from_NAND.svg.png)  | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/AND_from_NOR.svg/200px-AND_from_NOR.svg.png)

<br> 

### OR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/OR_ANSI_Labelled.svg/120px-OR_ANSI_Labelled.svg.png)

Implements logical disjunction. With inputs A and B and output C implements the logical expression C = A + B. Finds the maximum between two binary digits. C-like languages use the symbol | to denote bitwise OR.

 A | B | Q
 - | - | -
 0 | 0 | 0
 0 | 1 | 1
 1 | 0 | 1
 1 | 1 | 1

If no specific AND gates are available, one can be made from NAND or NOR gates shown in the image below.

NAND construction | NOR construction
- | -
![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/OR_from_NAND.svg/200px-OR_from_NAND.svg.png)  | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/OR_from_NOR.svg/200px-OR_from_NOR.svg.png)

<br>

### XOR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/XOR_ANSI_Labelled.svg/120px-XOR_ANSI_Labelled.svg.png)

Implements an exclusive or. With inputs A and B and output C implements the logical expression C = A ⊕ B. XOR represents the inequality function. C-like languages use the caret symbol ^ to denote bitwise XOR.

 A | B | Q
 - | - | -
 0 | 0 | 0
 0 | 1 | 1
 1 | 0 | 1
 1 | 1 | 0

 
If no specific XOR gates are available, one can be made from NAND or NOR gates shown in the image below.

NAND construction | NOR construction
- | -
![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/XOR_from_NAND.svg/300px-XOR_from_NAND.svg.png)  | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/XOR_from_NOR_2.svg/380px-XOR_from_NOR_2.svg.png)

---

# <a name="10"></a>10. Describe the XNOR, NAND and NOR gates
---

# <a name="11"></a>11. Present a circuit built of gates that will perform a specific function (depending on the appropriate combination of input data)
---

# <a name="12"></a>12. Describe the adder adding two bits, present its diagram
---

# <a name="13"></a>13. Present a scheme of size comparator that comparing two binary values (equality, and which of them is larger) and describe comparators
---

# <a name="14"></a>14. Draw a symbol, diagram with gates and describe how the SR latch works
---
## Circuit symbol
![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/94/SR_%28NAND%29_Flip-flop.svg/100px-SR_%28NAND%29_Flip-flop.svg.png)

## Diagram with two NOR gates
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/53/RS_Flip-flop_%28NOR%29.svg/200px-RS_Flip-flop_%28NOR%29.svg.png" style="display: inline; max-width: 400px"/>

*SR latch can be created with two NOR gates that have a cross-feedback loop.*


## Description
A **SR (Set-Reset) latch** serves as a memory device and is an asynchronous block. Therefore you must ensure that the combinational functions, which generate input signals for the latch, are race-free. Otherwise they may generate glitches, which may be latched, causing hazards in your system.

| S | R | Q | ¬Q | description
|- | - | - | - | -
| 0 | 0 <td colspan=2 style="text-align: center;">latched | the latch "latches" – it remains in its previously set or reset state.
| 0 | 1 | 0 | 1 | the Q output goes low (and ¬Q high), effectively resetting the latch's "memory"
| 1 | 0 | 1 | 0 | the Q output goes high (and Q low). The feedback mechanism, however, means that the Q output will remain high, even when the S input goes low again.
| 1 | 1 <td colspan=2 style="text-align: center;">**metastable** | race condition (explained below)
    
#### Race condition
The latch is being told to simultaneously produce a high Q and a low Q. This produces a "race condition" within the circuit - whichever flip flop succeeds in changing first will feedback to the other and assert itself. Ideally, both gates are identical and this is "metastable", and the device will be in an undefined state for an indefinite period. In real life, due to manufacturing methods, one gate will always win, but it's impossible to tell which it will be for a particular device from an assembly line. The state of S = R = 1 is therefore **"illegal"** and should never be entered.

# <a name="15"></a>15. Describe the SR flip-flop,
## The circuit symbol and the diagram
![](https://www.electronics-tutorials.ws/wp-content/uploads/2018/05/sequential-seq1.gif)
    
    
## Description
Flip-flop is a pair of latches (master and slave flop). 
    
---

# <a name="16"></a>16. Describe the D flip-flop and T flip-flop
### D flip-flop
The D-type flip-flop is a modified Set-Reset flip-flop with the addition of an inverter to prevent the S and R inputs from being at the same logic level.

![](https://www.electronics-tutorials.ws/wp-content/uploads/2018/05/sequential-seq6.gif)

---

# <a name="17"></a>17. Describe the multiplexer and demultiplexer,
---

# <a name="18"></a>18. Present a Karnaugh map for a given function, minimize it, write canonical normal forms (product and summative) forms of a function after minimizing it, draw a diagram,

---

# <a name="19"></a>Describe static-hazards
### Static hazard
A static hazard is the situation where, when one input variable changes, the output changes momentarily before stabilizing to the correct value. There are two types of static hazards:

- **Static-1 Hazard**: the output is currently 1 and after the inputs change, the output momentarily changes to 0,1 before settling on 1

- **Static-0 Hazard**: the output is currently 0 and after the inputs change, the output momentarily changes to 1,0 before settling on 0
In properly formed two-level AND-OR logic based on a Sum Of Products expression, there will be no static-0 hazards. Conversely, there will be no static-1 hazards in an OR-AND implementation of a Product Of Sums expression.

The most commonly used method to eliminate static hazards is to add redundant logic (consensus terms in the logic expression) with the help of Karnaugh map method.

### Example of a static hazard
Consider a simple imperfect circuit that suffers from a delay in the physical logic elements i.e. AND gates. It performs the function noting:

f = X1 * X2 + X1' * X3

If no delays were to occur, then the circuit would function normally. However, no two gates are ever manufactured identically. Due to this, the delay for the first AND gate will be slightly different than its counterpart. Thus an error occurs when the input changes from 111 to 011. i.e. when X1 changes state.

Now we know roughly how the hazard is occurring, for a clearer picture and the solution on how to solve this problem, we would look to the Karnaugh map. The two gates are shown by solid rings, and the hazard can be seen under the dashed ring. A theorem proved by Huffman[1] tells us that by adding a redundant loop 'X2X3' this will eliminate the hazard.

So our original function is now: f = X1 * X2 + X1' * X3 + X2 * X3