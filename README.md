# VHDL Counter Overflow Bug

This repository demonstrates a potential overflow bug in a simple VHDL counter. The counter is designed to increment from 0 to 10, but doesn't explicitly handle the case when it reaches 10 and continues to increment.

## Bug Description

The `counter` entity uses an `INTEGER` type with a range of 0 to 10 for its internal count.  However, when the counter reaches 10, it's still possible for the `internal_count <= internal_count + 1;` statement to execute.  This may lead to unexpected behavior, such as wrapping around to a very large number or causing a simulation error, depending on the VHDL simulator used.

## Bug Solution

The solution is to explicitly handle overflow cases by using a modulo operation or saturating the counter at its maximum value. The solution will prevent unexpected behavior, leading to a more robust and reliable counter.