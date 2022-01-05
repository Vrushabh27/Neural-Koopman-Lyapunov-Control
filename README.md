# Neural-Koopman-Lyapunov-Control

Code for our paper: Neural Koopman Lyapunov Control

## Requirements
- [dReal4: v4.19.02.1](https://github.com/dreal/dreal4)
- [PyTorch: 1.2.0](https://pytorch.org/get-started/locally/)

The learning framework consists of the learner and falsifier (or verifier). The learner simultaneously learns the Control Lyapunov Function (CLF), Koopman based observables (encoder), decoder and the matrices constituting the Koopman bilinear system. The falsifier (SMT solver) is used to generate counterexamples that do no satisfy the Control Lyapunov conditions (or satisfy the falsification constraint). These counterexamples are added to the training set. The process is repeated till the SMT solver is used to generate any counterexamples.

## A typical procedure is as follows:
- Define the neural network for the Control Lyapunov function (CLF), encoder (Koopman observables) and decoder.
- Collect data from the unknown nonlinear system and add them to the training set
- Set checking conditions for falsifier (falsification constraint)
- Start training and verifying 
- Procedure stops when no counterexample is found by the SMT solver
