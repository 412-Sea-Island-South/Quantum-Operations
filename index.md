***🦈 Introduction to Quantum Operations!🦈***
================================================
## What are Quantum Operations? 
Quantum Operations are operations used to manipulate quantum bits (or [qubits](https://en.wikipedia.org/wiki/Qubit), for short) in quantum circuits.
They include quantum gates (think of the classical **AND, OR, NOT** gates), as well as some operations that are not quantum gates, but still manipulate qubits.
A quantum gate, by the way, is just a basic circuit (i.e electrical pulses)operating on a small number of qubits.
They are the building blocks of quantum circuits, and can be put together like LEGOs.
There are different types of quantum gates, such as Clifford gates, and diagonal gates.
You can read more about Quantum Operations in [this article](https://www.medium.com/swlh/introduction-to-quantum-operations-e797fae3fab).

## Applying Quantum Operations: Creating a Superposition
We'll start off with the most basic thing possible, which is to create a simple superposition of two qubits.
We do this using the Hadamard gate.
It rotates the states |0⟩ and |1⟩ to the states |+⟩ and |-⟩, respectively. Lets see how it works!  
  
We'll head on over to [IBM Quantum Experience](https://quantum-computing.ibm.com), and open up the Quantum Composer.
First, we'll remove the extraneous qubits \(if there are any\), ad we'll be left with two qubits, q0 and q1.
We start by dragging-and-dropping the orange-ish Hadamard gate icon and putting it onto the q0 line.
Then, we add a CNOT gate to the two qubits, with the big plus-in-a-dot on the q1 line and the small dot on the q0 line.
Finally, we add measurement gates to the q0 and q1 lines.
And success!
You have created your first quantum circuit: a simple superposition!  
  
Now we'll move on to creating the W state, which is slightly harder.

### Reference Materials: Qiskit
This is the Qiskit code which you can open in the IBM Quantum Lab.
```python
from qiskit import *
qreg_q = QuantumRegister(2, 'q')
creg_c = ClassicalRegister(2, 'c')
circuit = QuantumCircuit(qreg_q, creg_c)

circuit.h(qreg_q[0])
circuit.cx(qreg_q[0]. qreg_q[1])
```

### Reference Materials: Gallery
<html>
  <h4 align="center">A Perfect Superposition of Qubits</h4>
  <p align="center">
    <img src="https://user-images.githubusercontent.com/81530826/118022442-392d0600-b311-11eb-81a8-0ec19d73cbe6.png">
  </p>
  <h4 align="center">A Superposition Circuit</h4>
  <p align="center">
    <img src="https://user-images.githubusercontent.com/81530826/118163642-1107da80-b3d7-11eb-8ccb-bc7939b48eab.png">
  </p>
</html>

## Applying Quantum Operations: The W State
Next, we will create the W state, which involves three qubits this time, as well s some new quantum operations. Namely, the NOT, RY, and U gates. In addition, we will also be using the "reset" gate.
W states are a way to entangle three qubits (basically superposition), just like the the superposition we created above.  

Once again, we go to [IBM Quantum](https://quantum-computing.ibm.com) and open up the Circuit Composer.
We'll start by resetting all the qubits to the |0⟩ state, which is done by applying the reset operation to each qubit.
Next, we'll apply the RY gate to the first qubit (which is q0).
The value of theta should be 1.9106332362490184.
Double click on the RY icon to change the value of theta.
After that, we'll apply the U gate to the second qubit (q1).
Once again, double click the gate icon to change the parameters.
Theta, Phi, Lambda, and Gamma should all be set to pi/2.
In addition, for the Qubit Connections, make sure q0 is connected to "c" and q1 is connect to "t".
Then we'll add a CNOT between q2 and q1, followed by a CNOT between q1 and q0.
Finally, we will add a NOT gate to q0.
And that completes the W state!
If you want, you can add measurement gates to all the qubits;
I didn't do this in order to show the superpositions.

### Reference Materials: Qiskit Code
### Reference Materials: Gallery
<html>
  <h4 align="center">A Superposition of 3 Qubits, the W State</h4>
  <p align="center">
    <img src="https://user-images.githubusercontent.com/81530826/118166798-ca1be400-b3da-11eb-940d-e9ba6862e5e7.png">
  </p>
  <h4 align="center">The W State Circuit</h4>
  <p align="center">
    <img src="https://user-images.githubusercontent.com/81530826/118166947-fb94af80-b3da-11eb-86eb-82bbafcdfa21.png">
  </p>
</html>
