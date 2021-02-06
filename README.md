# QuantumIBM-Algorithm-problem

This was the only code sequence out of a 2 qubit system that cave an output that was non zero because of the CNOT gate.  According to the simiulator I was supposed to recieve a 50-50 outcome of the 2 qubit system using a bit-flip or a sign error.  That is not what happened at all first problem was the IBM quantum machine transposed my code and did not enter in my original code.  Here is my original code:  (Please view in "raw") also *.ipnyb added.
-------------
Also the only quantum computer I have access to is IBM clouds, if it looks good in the classical machine but came out like this on the quantum machine, I see that either -1% was the error detection in the quantum computer, and that the bit "Barely flips", or I am not exactly sure how to interpret the results, especially with the code transpose which wasn't entered in by the circuit simulator.  The output looked good on the the 00 output 99.2% but the bit flipped .7x% of the time which was teh quantum machines errors, the classical machine expected equal distributions but what we have is a skewed distribution, or the <1% error was just something that we have to anticipate.  More experiments are needed.
--------------------------------------------------------------------
from qiskit import QuantumRegister, ClassicalRegister, QuantumCircuit
from numpy import pi

qreg_q = QuantumRegister(2, 'q')
creg_c = ClassicalRegister(2, 'c')
circuit = QuantumCircuit(qreg_q, creg_c)

circuit.reset(qreg_q[0])
circuit.reset(qreg_q[1])
circuit.h(qreg_q[0])
circuit.measure(qreg_q[1], creg_c[1])
circuit.sx(qreg_q[1])
circuit.z(qreg_q[0])
circuit.cx(qreg_q[0], qreg_q[1])

----------------------------------
What the computer transposed to the code to when I put in the job queue is this:

from qiskit import QuantumRegister, ClassicalRegister, QuantumCircuit
from numpy import pi

qreg_q = QuantumRegister(5, 'q')
creg_c = ClassicalRegister(2, 'c')
circuit = QuantumCircuit(qreg_q, creg_c)

circuit.rz(1.5707963267948966, qreg_q[0])
circuit.sx(qreg_q[0])
circuit.rz(4.712388980384688, qreg_q[0])
circuit.measure(qreg_q[1], creg_c[1])
circuit.sx(qreg_q[1])
circuit.cx(qreg_q[0], qreg_q[1])


-----------------------------------------

Attached is some screenshots.
