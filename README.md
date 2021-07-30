# QG8
QG8 is a lightweight format for storing and exchanging numerical tensor data and data flow graphs in a binary format. It was created as way to store quantum models and data in a single file, including quantum gate and quantum circuit specifications, control pulse definitions, time independent and time-dependent model Hamiltonians, device characteristics, calibration data and noise models, user defined control flow instructions and simulation or measurement results. This facilitates numerical simulation and optimization of quantum problems as well as interfacing with quantum computers.

A QG8 file consists of a header and a collection of chunks that encode a directed acyclic graph. Each chunk can represent either a *tensor node* (containing numerical tensor data and an associated header) acting as an input or placeholder, an *op node* which does not contain data but specifies operations that should be performed on the data, or an *adjacency tensor* indicating how information flows through the graph. The advantage of this approach is that it allows to store all the data as well as the instructions on how to perform computations on the data in a single object which can then easily be exchanged between different systems.

**Key features:**
- Efficient storage of real or complex valued scalars, vectors, matrices and higher rank tensors using sparse packing and dynamically assigned index data types.

- Uncompressed binary format for fast file I/O, which can be further compressed to save space and allow for transmission of large problems physically or over networks.

- Possibility to load individual nodes or to iteratively read a graph without necessarily loading the entire file into the computer's memory or RAM.

- Tensor data can be stored as integers, single or double precision floating point numbers and complex numbers.

- Practically no storage limits. QG8 can in principle store an unlimited number of tensors with rank <2<sup>16</sup>, each containing up to 2<sup>64</sup> nonzero elements.

- Accommodates any tensor format that can be exported as a list of indices and values, including custom packing formats, e.g., to efficiently store symmetric or Hermitian matrices.

- Chunks or graph nodes can be additionally specified by flags and an optional string label to facilitate integration and use.

- Open format with libraries for fast and convenient integration into Python and C/C++ code.

-----

**This repository contains one document:
[QG8 file specification and programmers reference](QG8_Specification_v1.pdf)**

-----


# QG8 Libraries
## Python 
https://github.com/aQCess/QG8-Python

## C/C++ 
https://github.com/aQCess/QG8-C
