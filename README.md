# EpiRes
Epistemic Reasoner based on Resolution of Modal Clauses

Author: Thomas R. Ioerger

Contact: ioerger@cs.tamu.edu

Reference: (eventually)

Installation
------------

This is a C++ program that should compiled 
It does not use a fancy generic makefile (e.g. with configure), 
just a simple makefile. (I hope it works on a wide enough range of platforms).

Dependencies: none (except g++?)

You should be able to compile it by just typing 'make'.

Background
----------

Does inference on (propositional) modal logic KD by resolution refutation.
(negate query, see if you can derive the empty clause as contradiction)

KD language has this syntax:

KB's can be written in an ASCII version using syntax based on S-expressions
(prefix notation, lists with operator followed by args)
modal operators are expressed as [i], <i>, K:i, or P:i, where i is 
a string representing an index (typically, and agent name).

Key is algorithm for resolving 2 modal clauses together,
which extends tranditional propositional resolution to handle modal operators

Modal clauses extend propositional clauses with this syntax,
which allows them to have nested sub-expressions.

mclause BNF


Note: even single propositions must be in 'or's (unit clauses).


For writing KB files, it is more convenient to add connectives
and relax the constraints, to get the expressiveness of 
arbitrary propositional sentences.
Here, asserting lone propositions (facts) are fine.



The there is a pre-processing python script, convCNF.py, that converts
the modal-propositional sentences to modal-CNF.



Usage
-----

files and/or clauses on command line

(note: you might want to run them through convCNF.py, becuase they have
to conform to modal-clauses syntax)

Flags



Example
-------

explain the output

add KB file (examples/.kb, .cnf, .out)


API 
---

explain the code 

* Expr class (represents clauses)
* validate()
* modal_resolvable()
* model_resolve_rec()=zipper
* ResPairs
* propagate_empty_clauses()
* inconsistent()
* provenance, ancestors
