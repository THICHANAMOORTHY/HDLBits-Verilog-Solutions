# HDLBits - 7458 Chip

## Problem

Implement the functionality of the **7458** IC using Verilog.

The 7458 consists of:
- Four 2-input AND gates
- Two OR gates

Outputs:
- p1y = (p1a & p1b & p1c) | (p1d & p1e & p1f)
- p2y = (p2a & p2b) | (p2c & p2d)

## Logic Diagram

![Circuit](circuit.png)

## Timing Diagram

![Timing Diagram](timing_diagram.png)

## Verilog Solution

```verilog
module top_module (
    input p1a, p1b, p1c, p1d, p1e, p1f,
    output p1y,
    input p2a, p2b, p2c, p2d,
    output p2y );

    wire ab;
    wire cd;
    wire ef;
    wire gh;

    assign ab = p2a & p2b;
    assign cd = p1a & p1b & p1c;
    assign ef = p1d & p1e & p1f;
    assign gh = p2c & p2d;

    assign p1y = cd | ef;
    assign p2y = ab | gh;

endmodule
```

## Boolean Expressions

```
p1y = (p1a · p1b · p1c) + (p1d · p1e · p1f)

p2y = (p2a · p2b) + (p2c · p2d)
```

## Concepts Practiced

- Continuous assignments (`assign`)
- AND (`&`) operator
- OR (`|`) operator
- Intermediate wires
- Gate-level logic implementation

## Result

✔ HDLBits Accepted
