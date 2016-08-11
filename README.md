
# Specification of the .qc file format

The header information consists of the following:

* `.v`: Defines names for the circuit lines.
* `.i`: Input lines of the circuit. (Optional parameter).
* `.o`: Output lines of the circuit. (Optional parameter).
* `.ol`: Allows one to alternate names to be specified for the output labels. (Optional parameter).
* `.c`: Specifies the values of input constants. (Optional parameter).

Gates are listed between the `BEGIN` and `END` tags. The gate name is
represented as the leftmost word on each line. The rightmost word refers to the
circuit line on which the gate is targeted.  The rest of the numbers words to
the lines on which the gate is controlled. If a control specifier is followed
by the `'` symbol.

## Gates

* `tof`: Toffoli gate. Will accept an arbitrary number of controls.
* `cnot`: Cnot gate. Must have a single control.
* `not`: Not gate. Must have zero controls.

Any other single character symbol can be used to represent a gate.
The character will be used as a symbol to represesnt the gate when drawing the circuit.


## Examples

```
.v a b
BEGIN
H a
tof a b
END
```
