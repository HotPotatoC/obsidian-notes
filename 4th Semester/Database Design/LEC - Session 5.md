Class: [[COMP6481001 - Database Design]]
Session: 
Topics: 
Date: 2023-03-27
Lecturer: [[4th Semester/Lecturers/D6659 - EKO SETYO PURWANTO, S.Pd., M.Kom.]]

# Advanced Normalization

Armstrong's Axiom is a set of inference rules

Let A, B, and C be subsets of the attributes of the relation R. Armstrong's axioms are as follows:
- Reflexity: If B is a subset of A, then A -> B
- Augmentation: If A -> B, then A,C -> B,C
- Transitivity: If A -> B and B -> C, then A -> C
- Self-determination: A->A
- Decomposition: If A -> B,C, then A -> B and A -> C
- Union: If A-> B and A-> C, then A -> B,C

# Boyce-Codd Normal Form (BCNF)

Based on functional dependencies that take into account all candidate keys in a relation, however BCNF also has additional constraints compared with the general definition of 3NF.

A relation is in BCNF if and only if every determinant is a candidate key.

The difference between 3NF and BCNF is that for a functional dependency A -> B, 3NF allows this dependency in a relation if B is a primary-key attribute and A is not a candidate key. Whereas, BCNF insists that for this deppendency to remain in a relation, A must be a candidate key.