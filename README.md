# Regularized Sphere Decoding for Integer Least Squares Problems

This software implements a depth-first search sphere decoding algorithm to solve regularized integer least squares (ILS)
problems with L0 and L1 norm regularizations. It is designed for applications in signal processing, communications, compressed 
sensing, and other fields requiring sparse or regularized solutions. The primary objective of this project is to develop an 
efficient algorithm for solving the standard L1/L0 and the overdetermined box-constrained L0 norm regularized integer least 
squares problems. This problem is crucial
in various applications, including digital communications, compressed sensing, and signal processing. The goal
is to minimize the Euclidean distance between the observed signal and a linear transformation of the integer
vector, while also incorporating either an L1 or L0 regularization term to promote sparsity. This project will
build upon the Pohst enumeration strategy, which describes a method for solving the unregularized integer
least squares problem. For a more detailed description and the derivations, see the included PDF document.

## Features

- Efficient depth-first search using sphere decoding.
- Support for both L0 and L1 norm regularizations.
- Retrieve top \(p\) solutions, ranked by objective value.
- Highly documented

## Usage

### Inputs

- R: n-by-n real nonsingular upper triangular matrix
- y: n-dimensional real vector
- lambda: positive scalar, the regularization parameter for the \ell_1 norm
- p: the number of optimal solutions (default value: 1)

#### For Box Constrained Problem:

- l: n-dimensional integer vector, lower bound
- u: n-dimensional integer vector, upper bound

### Output
- Zhat: n-by-p integer matrix (in double precision), whose j-th column is the j-th optimal solution. Solutions are ordered such that the residual with the regularization term satisfies: ||y - R*Zhat(:,1)|| + lambda * ||Zhat(:,1)||_1 <= ||y - R*Zhat(:,p)|| + lambda * ||Zhat(:,p)||_1.
