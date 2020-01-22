## Quick reference

- [Present the given number in the NKB, BCD, U1, U2 codes as positive and negative value](#present-the-given-number-in-the-nkb-bcd-u1-u2-codes-as-positive-and-negative-value)
  - [NBC (NBK)- Natural Binary Code](#nbc-nbk--natural-binary-code)
  - [Gray Code](#gray-code)
  - [1's Complement (U1)](#1s-complement-u1)
  - [2's Complement (U2)](#2s-complement-u2)
- [Present the given number in hexadecimal code](#present-the-given-number-in-hexadecimal-code)
  - [Hexadecimal code](#hexadecimal-code)
- [Present the given number as negative in the 2'complement](#present-the-given-number-as-negative-in-the-2complement)
- [Perform simple calculations for two numbers in the 1'complement](#perform-simple-calculations-for-two-numbers-in-the-1complement)
  - [Subtraction in U1](#subtraction-in-u1)
- [Perform simple calculations for two numbers in the 2'complement](#perform-simple-calculations-for-two-numbers-in-the-2complement)
  - [Addition in U2](#addition-in-u2)
- [Multiplication of two binary numbers](#multiplication-of-two-binary-numbers)
- [Adding two numbers in the BCD and EXCESS-3 code](#adding-two-numbers-in-the-bcd-and-excess-3-code)
  - [BCD](#bcd)
  - [Excess-3](#excess-3)
- [Negating numbers in the BCD and EXCESS-3 code](#negating-numbers-in-the-bcd-and-excess-3-code)
- [Describe the AND, OR and XOR gates](#describe-the-and-or-and-xor-gates)
  - [AND gate](#and-gate)
    - [Alternatives](#alternatives)
  - [OR gate](#or-gate)
    - [Alternatives](#alternatives-1)
  - [XOR gate](#xor-gate)
    - [Alternatives](#alternatives-2)
- [Describe the XNOR, NAND and NOR gates](#describe-the-xnor-nand-and-nor-gates)
  - [XNOR gate](#xnor-gate)
    - [Alternatives](#alternatives-3)
  - [NAND gate](#nand-gate)
    - [Alternatives](#alternatives-4)
  - [NOR gate](#nor-gate)
    - [Alternatives](#alternatives-5)
- [Present a circuit built of gates that will perform a specific function (depending on the appropriate combination of input data)](#present-a-circuit-built-of-gates-that-will-perform-a-specific-function-depending-on-the-appropriate-combination-of-input-data)
- [Describe the adder adding two bits, present its diagram](#describe-the-adder-adding-two-bits-present-its-diagram)
- [Present a scheme of size comparator that comparing two binary values (equality, and which of them is larger) and describe comparators](#present-a-scheme-of-size-comparator-that-comparing-two-binary-values-equality-and-which-of-them-is-larger-and-describe-comparators)
- [Draw a symbol, diagram with gates and describe how the SR latch works](#draw-a-symbol-diagram-with-gates-and-describe-how-the-sr-latch-works)
  - [Circuit symbol](#circuit-symbol)
  - [Diagram with two NOR gates](#diagram-with-two-nor-gates)
  - [Description](#description)
      - [Race condition](#race-condition)
- [Describe the SR flip-flop](#describe-the-sr-flip-flop)
  - [The circuit symbol and the diagram](#the-circuit-symbol-and-the-diagram)
  - [Description](#description-1)
- [Describe the D flip-flop and T flip-flop](#describe-the-d-flip-flop-and-t-flip-flop)
  - [D flip-flop](#d-flip-flop)
  - [T flip-flop](#t-flip-flop)
- [Describe the multiplexer and demultiplexer](#describe-the-multiplexer-and-demultiplexer)
  - [Multiplexer](#multiplexer)
  - [Demultiplexer](#demultiplexer)
- [Present a Karnaugh map for a given function, minimize it, write canonical normal forms (product and summative) forms of a function after minimizing it, draw a diagram](#present-a-karnaugh-map-for-a-given-function-minimize-it-write-canonical-normal-forms-product-and-summative-forms-of-a-function-after-minimizing-it-draw-a-diagram)
  - [Karnaugh map](#karnaugh-map)
  - [Minimized function](#minimized-function)
  - [Diagram of the minimized function](#diagram-of-the-minimized-function)
- [Describe static-hazards](#describe-static-hazards)
  - [Static hazard](#static-hazard)
  - [Example of a static hazard](#example-of-a-static-hazard)

Present the given number in the NKB, BCD, U1, U2 codes as positive and negative value
===
**Note for each one: It is important to leave the first bit of each 'open' to signify the sign.**
## NBC (NBK)- Natural Binary Code
It is important to leave the first bit of each 'open' to signify the sign.

It is just a binary representation of a number with predetermined number of bits. Example:<br>
67 into 8-bit natural binary code:<br>
01000011

## Gray Code
It is obtained by shifting the NBC number by 1 to the left and performing XOR on the new number with the unshifted one and discarding the last bit of the original. Example: <br>
001000011 - NBC<br>
01000011 - NBC shifted<br>
01100010 - Gray code<br>

## 1's Complement (U1)
To obtain this complement we need to take each bit of the number and switch to the opposite. Example:<br>
01000011 - NBC<br>
10111100 - 1's Complement

## 2's Complement (U2)
To obtain this complement we first need to get 1's complement then add 1. Example:<br>
01000011 - NBC<br>
10111100 -1's Complement<br>
10111101 -2's Complement<br>

**NOTE: Both in U1 and U2 a positive number is represented the same as NBC, negatives, as described above.**

Present the given number in hexadecimal code
===
## Hexadecimal code
It is a number system of base 16, it shares numbers 0-9 with the decimal system, larger numbers are represented with letters A-F.

The easiest method to convert a number into HEX is to first convert it into binary, then create groups of 4 bits, starting from bit standing at 2^0, and calculate the values. Example:<br>
67 - decimal<br>
01000011 - 8-bit NBC<br>
0100 | 0011 - 2 groups of 4 bits<br>
&nbsp;&nbsp;4&nbsp;&nbsp;&nbsp;3 - values of the groups<br>
 43 - HEX <br>

Present the given number as negative in the 2'complement
===
Following the instructions above: <br>
67 - decimal positive<br>
01000011 - 8-bit NBC<br>
10111100 - 1's Complement<br>
10111101 - 2's Complement = -67 in decimal <br>

Perform simple calculations for two numbers in the 1'complement
===
## Subtraction in U1
It's just addition with one of the numbers 'flipped' to U1.
Addition is the same as in NBC, but if there exists a carry it is added at the end. Example: <br>
-67 10111100<br>
+68 01000100<br><br>
1 00000000 - incorrect sum, carry<br>
00000001 - correct sum after correction 

Perform simple calculations for two numbers in the 2'complement
===
Operations in U2 follow the same rules as in U1, except in the case of a carry existing, it is discarded.
## Addition in U2
Example:<br>
-67 10111101<br>
+68 01000100<br><br>
 1 - carry is discarded<br>
00000001 - correct sum <br>

Multiplication of two binary numbers
===
Numbers in binary are multiplied similarly to decimal, we simply rewrite the first number under every 1 of the second, shifting it, so it starts at the same 'spot' as the 1, and then adding them. Example:<br><br>
 67 01000011<br>
 *5 00000101<br><br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;01000011<br>
 	&#43; 01000011<br>
 &nbsp;&nbsp;&nbsp;0101001111 = 335 <br>

Adding two numbers in the BCD and EXCESS-3 code
===
## BCD
In this code, each decimal digit is represented by 4 binary bits corresponding to that digit. Example:<br>
67 - decimal<br>
0110 0111 - BCD code <br>

## Excess-3
It is a modified BCD code, instead of representing the digit itself, we represent digit greater than original by 3. Example:<br>
67 - decimal<br>
9 10 - digits increased by 3<br>
1001 1010 - Excess-3 <br>

Negating numbers in the BCD and EXCESS-3 code
===

Describe the AND, OR and XOR gates
===
## AND gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/AND_ANSI_Labelled.svg/120px-AND_ANSI_Labelled.svg.png)

Implements logical conjunction. With inputs A and B and output C implements the logical expression C = A · B. Finds the minimum between two binary digits. C-like languages use the symbol & to denote bitwise AND.

 | A   | B   | A AND B |
 | --- | --- | :-----: |
 | 0   | 0   |    0    |
 | 0   | 1   |    0    |
 | 1   | 0   |    0    |
 | 1   | 1   |    1    |

### Alternatives

| NAND construction                                                                                                          | NOR construction                                                                                                         |
| -------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/AND_from_NAND.svg/200px-AND_from_NAND.svg.png) | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/AND_from_NOR.svg/200px-AND_from_NOR.svg.png) |
*If no specific AND gates are available, one can be made from NAND or NOR gates shown in the image above.*

## OR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/OR_ANSI_Labelled.svg/120px-OR_ANSI_Labelled.svg.png)

Implements logical disjunction. With inputs A and B and output C implements the logical expression C = A + B. Finds the maximum between two binary digits. C-like languages use the symbol | to denote bitwise OR.

 | A   | B   | A OR B |
 | --- | --- | :----: |
 | 0   | 0   |   0    |
 | 0   | 1   |   1    |
 | 1   | 0   |   1    |
 | 1   | 1   |   1    |

### Alternatives

| NAND construction                                                                                                        | NOR construction                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/OR_from_NAND.svg/200px-OR_from_NAND.svg.png) | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4b/OR_from_NOR.svg/200px-OR_from_NOR.svg.png) |
*If no specific OR gates are available, one can be made from NAND or NOR gates shown in the image above.*

## XOR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/XOR_ANSI_Labelled.svg/120px-XOR_ANSI_Labelled.svg.png)

Implements an exclusive or. With inputs A and B and output C implements the logical expression C = A ⊕ B. XOR represents the inequality function. C-like languages use the caret symbol ^ to denote bitwise XOR.

 | A   | B   | A XOR B |
 | --- | --- | :-----: |
 | 0   | 0   |    0    |
 | 0   | 1   |    1    |
 | 1   | 0   |    1    |
 | 1   | 1   |    0    |

### Alternatives

| NAND construction                                                                                                          | NOR construction                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/XOR_from_NAND.svg/300px-XOR_from_NAND.svg.png) | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5e/XOR_from_NOR_2.svg/380px-XOR_from_NOR_2.svg.png) |
*If no specific XOR gates are available, one can be made from NAND or NOR gates shown in the image above.*

Describe the XNOR, NAND and NOR gates
===
## XNOR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/3/35/Xnor-gate-en.svg/278px-Xnor-gate-en.svg.png)

Implements logical equality. With inputs A and B and output C implements the logical expression C = A ⨀ B. C-like languages use the operator == to denote XNOR on booleans.

 | A   | B   | A XNOR B |
 | --- | --- | :------: |
 | 0   | 0   |    1     |
 | 0   | 1   |    0     |
 | 1   | 0   |    0     |
 | 1   | 1   |    1     |

### Alternatives

| NAND construction                                                                                                            | NOR construction                                                                                                           |
| ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/XNOR_from_NAND.svg/380px-XNOR_from_NAND.svg.png) | ![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f0/XNOR_from_NOR.svg/300px-XNOR_from_NOR.svg.png) |
*If no specific XNOR gates are available, one can be made from NAND or NOR gates shown in the image above.*

## NAND gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/NAND_ANSI_Labelled.svg/120px-NAND_ANSI_Labelled.svg.png)

The NAND is a universal, functionally complete gate: any boolean function can be implemented by using a combination of NAND gates. *This also applies to the NOR gate.*

The function NAND(a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>) is logically equivalent to NOT(a<sub>1</sub> AND a<sub>2</sub> AND ... AND a<sub>n</sub>).

 | A   | B   | A NAND B |
 | --- | --- | :------: |
 | 0   | 0   |    1     |
 | 0   | 1   |    1     |
 | 1   | 0   |    1     |
 | 1   | 1   |    0     |

### Alternatives

NOR construction |
- |
![](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2b/NAND_from_NOR.svg/280px-NAND_from_NOR.svg.png) |
*If no specific NAND gates are available, one can be made from NOR gates shown in the image above.*

## NOR gate

![alternate text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/NAND_ANSI_Labelled.svg/120px-NAND_ANSI_Labelled.svg.png)

The NOR gate implements logical NOR. Just like NAND, it's a functionally complete gate: any boolean function can be implemented by using a combination of NOR gates.

The function NAND(a<sub>1</sub>, a<sub>2</sub>, ..., a<sub>n</sub>) is logically equivalent to NOT(a<sub>1</sub> AND a<sub>2</sub> AND ... AND a<sub>n</sub>).

 | A   | B   | A NOR B |
 | --- | --- | :-----: |
 | 0   | 0   |    1    |
 | 0   | 1   |    0    |
 | 1   | 0   |    0    |
 | 1   | 1   |    0    |

### Alternatives

NAND construction |
- |
![](https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/NOR_from_NAND.svg/280px-NOR_from_NAND.svg.png) |
*If no specific NOR gates are available, one can be made from NAND gates shown in the image above.*

Present a circuit built of gates that will perform a specific function (depending on the appropriate combination of input data)
===

Describe the adder adding two bits, present its diagram
===

Present a scheme of size comparator that comparing two binary values (equality, and which of them is larger) and describe comparators
===

Draw a symbol, diagram with gates and describe how the SR latch works
===

## Circuit symbol
![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/94/SR_%28NAND%29_Flip-flop.svg/100px-SR_%28NAND%29_Flip-flop.svg.png)

## Diagram with two NOR gates
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/5/53/RS_Flip-flop_%28NOR%29.svg/200px-RS_Flip-flop_%28NOR%29.svg.png" style="display: inline; max-width: 400px"/>

*SR latch can be created with two NOR gates that have a cross-feedback loop.*


## Description
A **SR (Set-Reset) latch** serves as a memory device and is an asynchronous block. Therefore you must ensure that the combinational functions, which generate input signals for the latch, are race-free. Otherwise they may generate glitches, which may be latched, causing hazards in your system.

| S   | R                                                          | Q                                                                      | ¬Q  | description                                                                                                                                          |
| --- | ---------------------------------------------------------- | ---------------------------------------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| 0   | 0 <td colspan=2 style="text-align: center;">latched        | the latch "latches" – it remains in its previously set or reset state. |
| 0   | 1                                                          | 0                                                                      | 1   | the Q output goes low (and ¬Q high), effectively resetting the latch's "memory"                                                                      |
| 1   | 0                                                          | 1                                                                      | 0   | the Q output goes high (and Q low). The feedback mechanism, however, means that the Q output will remain high, even when the S input goes low again. |
| 1   | 1 <td colspan=2 style="text-align: center;">**metastable** | race condition (explained below)                                       |
    
#### Race condition
The latch is being told to simultaneously produce a high Q and a low Q. This produces a "race condition" within the circuit - whichever flip flop succeeds in changing first will feedback to the other and assert itself. Ideally, both gates are identical and this is "metastable", and the device will be in an undefined state for an indefinite period. In real life, due to manufacturing methods, one gate will always win, but it's impossible to tell which it will be for a particular device from an assembly line. The state of S = R = 1 is therefore **"illegal"** and should never be entered.

Describe the SR flip-flop
===
## The circuit symbol and the diagram
![](https://www.electronics-tutorials.ws/wp-content/uploads/2018/05/sequential-seq1.gif)
    
## Description
Flip-flop is a pair of latches (master and slave flop). 

todo

Describe the D flip-flop and T flip-flop
===
## D flip-flop
The D-type flip-flop is a modified Set-Reset flip-flop with the addition of an inverter to prevent the S and R inputs from being at the same logic level.

![](https://www.electronics-tutorials.ws/wp-content/uploads/2018/05/sequential-seq6.gif)

## T flip-flop

todo

Describe the multiplexer and demultiplexer
===
## Multiplexer
todo

## Demultiplexer

todo

Present a Karnaugh map for a given function, minimize it, write canonical normal forms (product and summative) forms of a function after minimizing it, draw a diagram
===
## Karnaugh map
todo

## Minimized function
todo

## Diagram of the minimized function
todo

Describe static-hazards
===
## Static hazard
A static hazard is the situation where, when one input variable changes, the output changes momentarily before stabilizing to the correct value. There are two types of static hazards:

- **Static-1 Hazard**: the output is currently 1 and after the inputs change, the output momentarily changes to 0,1 before settling on 1

- **Static-0 Hazard**: the output is currently 0 and after the inputs change, the output momentarily changes to 1,0 before settling on 0
In properly formed two-level AND-OR logic based on a Sum Of Products expression, there will be no static-0 hazards. Conversely, there will be no static-1 hazards in an OR-AND implementation of a Product Of Sums expression.

The most commonly used method to eliminate static hazards is to add redundant logic (consensus terms in the logic expression) with the help of Karnaugh map method.

## Example of a static hazard
Consider a simple imperfect circuit that suffers from a delay in the physical logic elements i.e. AND gates. It performs the function noting:

f = X1 * X2 + X1' * X3

If no delays were to occur, then the circuit would function normally. However, no two gates are ever manufactured identically. Due to this, the delay for the first AND gate will be slightly different than its counterpart. Thus an error occurs when the input changes from 111 to 011. i.e. when X1 changes state.

Now we know roughly how the hazard is occurring, for a clearer picture and the solution on how to solve this problem, we would look to the Karnaugh map. The two gates are shown by solid rings, and the hazard can be seen under the dashed ring. A theorem proved by Huffman tells us that by adding a redundant loop 'X2X3' this will eliminate the hazard.

So our original function is now: f = X1 * X2 + X1' * X3 + X2 * X3