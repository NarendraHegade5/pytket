Changelog
==================================
0.4.1 (December 2019)
---------------------
New Features:

* New classes for placement of logical qubits from :py:class:`Circuit` to physical qubits from :py:class:`Device` or :py:class:`Architecture`

Updates:

* Updated documentation and additional examples
* OptimiseCliffordsZX pass removed, FullPeepholeOptimise pass added
* New architectures added, including :py:class:`SquareGrid`, :py:class:`HexagonalGrid`, :py:class:`RingArch`, :py:class:`TriangularGrid` and :py:class:`CyclicButterfly`
* Device information from :py:class:`Device` can now be returned
* Stability improvements and bug fixes

0.4.0 (November 2019)
---------------------
New Features:

* Contractural compilation passes with guarantees on how they transform circuits that satisfy their preconditions. This provides a uniform interface for optimisations, routing, and other stages of compilation
* New "Box" gate types for encapsulating high-level structures (arbitrary subcircuits, parametrised composite gate definitions, unitaries, Pauli operators)
* Simpler and more flexible structure for registers and names of qubits/bits, allowing for non-contiguous and multi-dimensional indices (referring to individual units, linear registers, grids, etc.)
* Latex diagram output using Quantikz
* The :py:class:`Device` class to build on top of :py:class:`Architecture` with error and timing information
* Initial and final maps tracked throughout the entire compilation procedure using the :py:class:`CompilationUnit` wrapper
* Import circuits from Quipper source files
* Utility methods for processing data from Backends

Updates:

* All Backends refactored for more consistent interfaces, separation of data processing, and introducing batch circuit processing when possible
* Routing improved to use distributed CX (BRIDGE) gates in addition to SWAP insertion
* Cost function for noise-aware allocation of qubits improved to consider more sources of noise
* :py:class:`Architecture` objects can be specified with arbitrary node names, using the same :py:class:`UnitID` objects and qubits/bits
* Removed the :py:class:`PhysicalCircuit` class in preference of just using :py:class:`Circuit` objects
* Generalised and sped up the gate commutation pass
* Optimisation for redundant gate removal now removes diagonal gates before measurements
* Support for custom gate definitions in QASM input
* Support for a greater fragment of sympy expressions in gate parameters
* Stability improvements and bug fixes
* Updated documentation and additional examples

0.3.0 (August 2019)
-------------------
New Features:

* More options for circuit routing, including noise-aware allocation of qubits
* Basic support for generating circuits with classical conditions and multiple registers
* ForestBackend for running circuits on Rigett's QVM simulators and QCS
* AerUnitaryBackend for inspecting the full unitary of a circuit
* Chaining gate commands
* Primitive QASM<->Circuit (import and export)

Updates:

* Simplified conversions for pytket_qiskit, going straight to/from QuantumCircuit rather than DAGCircuit
* CSWAP gate added

0.2.3 (July 2019)
------------------
New Features:

* Decomposition `Transform` for controlled gates

Updates:

* Exposed additional gate types into Pytket
* Fixed bug in `add_circuit`
* Fixed routing bug
* Made `run` behaviour more sensible for backends

0.2.2 (June 2019)
------------------
Updates:

* Minor bug fixes, examples and documentation

0.2.1 (June 2019)
------------------
Updates:

* Extra support for appending Circuits from Matrices and Exponents
* More docs and examples
* Fixed bugs in backends

0.2.0 (June 2019)
------------------
New Features:

* Support for circuits and simulation using ProjectQ (0.4.2)
* Support for conversion to and from PyZX (https://github.com/Quantomatic/pyzx)
* Interface to many new optimisation passes, allowing for custom passes
* Circuit compilation using symbolic parameters
* New interface to routing
* Enabled noise modeling in the AerBackend module

Updates:

* Qiskit support updated for Qiskit 0.10.1 and Qiskit Chemistry 0.5
* Pytket Chemistry module has been removed, to be part of the separate Eumen package
* Bug fixes and performance improvements to routing

0.1.6 (April 2019)
------------------
Updates:

* Routing can return SWAP gates rather than decomposing to CNOTs
* Decomposition and routing bug fixes

0.1.5 (April 2019)
------------------
New Features:

* Enabled conversions from 4x4 unitary matrices to 2 qubit circuit

0.1.4 (April 2019)
------------------
Updates:

* Bug fix patch for routing and performance improvements

0.1.3 (March 2019)
------------------
Updates:

* Qiskit support updated for Terra 0.7.3, Aqua 0.4.1, and Chemistry 0.4.2
* Bug fixes in routing

0.1.2 (February 2019)
---------------------
New Features:

* Support for circuits from Rigetti pyQuil (2.3)
* New interface for constructing and analysing circuits in pytket directly
* Named classical registers for measurements

Updates:

* Documentation and tutorial improvements
* Bug fixes in routing and optimisations
* Minor API changes for notational consistency

0.1.0 (December 2018)
---------------------
New Features:

* Support for circuits and architectures from IBM Qiskit (0.7)
* ``pytket.qiskit.TketPass`` allows pytket to be plugged in to the Qiskit compilation stack to take advantage of t|ket>'s routing and optimisations
* New Chemistry package featuring an implementation of the Quantum Subspace Expansion to work within or alongside Qiskit Aqua (0.4)
* Optimisation passes introduced for powerful circuit rewriting before routing, and safe rewriting after routing

Updates:

* Cirq functionality supports Cirq 0.4
* Refactoring into modules

0.0.1 (July 2018)
-----------------
New Features:

* Support for circuits and architectures from Google Cirq (0.3)
* Routing and placement procedures available for manipulating circuits to satisfy device specifications
