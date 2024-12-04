# VHDL Counter with Integer Overflow Bug

This repository demonstrates a subtle integer overflow bug in a VHDL counter.  The counter increments correctly until it reaches its maximum value (15 in this case).  Incrementing beyond the maximum value causes an overflow, resulting in unpredictable behavior. This is a common issue in hardware description languages, and thorough testing is necessary to identify these potential errors.

## Bug Description
The `buggy_counter.vhd` file contains the VHDL code for the buggy counter. The issue lies in the increment operation (`internal_count <= internal_count + 1;`). When `internal_count` reaches 15, the next increment should reset it to 0. However, if the integer type is not handled correctly, or if a larger increment occurs, it could lead to an unexpected value.

## Solution
The `fixed_counter.vhd` file provides a corrected version of the counter. The fix ensures that the counter correctly wraps around to 0 after reaching the maximum value.