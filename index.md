Introduction to Quantum Operations
==================================
## What are Quantum Operations?
Quantum Operations are operations used to manipulate quantum bits (or [qubits](https://en.wikipedia.org/wiki/Qubit), for short) in quantum circuits.
They include quantum gates (think of the classical **AND, OR, NOT** gates), as well as some operations that are not quantum gates, but still manipulate qubits.
A quantum gate, by the way, is just a basic circuit (i.e electrical pulses)operating on a small number of qubits.
They are the building blocks of quantum circuits, and can be put together like LEGOs.
There are different types of quantum gates, such as Clifford gates, and diagonal gates.
You can read more about Quantum Operations in [my article](https://www.medium.com/swlh/introduction-to-quantum-operations-e797fae3fab).

## Applying Quantum Operations
### Creating a Superposition
We'll start off with the most basic thing possible, which is to create a simple superposition of two qubits.
We do this using the Hadamard gate.
It rotates the states |0⟩ and |1⟩ to the states |+⟩ and |-⟩, respectively.  
Lets see how it works!  

#### IBM Quantum Experience
We'll head on over to [IBM Quantum Experience](https://quantum-computing.ibm.com), and open up the Quantum Composer.
First, we'll remove the extraneous qubits \(if there are any\), ad we'll be left with two qubits, q0 and q1.
We start by dragging-and-dropping the orange-ish Hadamard gate icon and putting it onto the q0 line.
Then, we add a CNOT gate to the two qubits, with the big plus-in-a-dot on the q1 line and the small dot on the q0 line.
Finally, we add measurement gates to the q0 and q1 lines.  
Success!
You have created your first quantum circuit: a simple superposition!  
We'll move on to creating a Bell state, which is slightly harder.

#### Qiskit Code
This is the Qiskit code which you can open in the IBM Quantum Lab.
```python
from qiskit import *
qreg_q = QuantumRegister(2, 'q')
creg_c = ClassicalRegister(2, 'c')
circuit = QuantumCircuit(qreg_q, creg_c)

circuit.h(qreg_q[0])
circuit.cx(qreg_q[0]. qreg_q[1])
```

#### Measurement Probabilities
