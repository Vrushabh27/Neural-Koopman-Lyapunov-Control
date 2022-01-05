# Neural-Koopman-Lyapunov-Control

Code for our paper: Neural Koopman Lyapunov Control

## Requirements
- [dReal4: v4.19.02.1](https://github.com/dreal/dreal4)
- [PyTorch: 1.2.0](https://pytorch.org/get-started/locally/)

The learning framework consists of the learner and falsifier (or verifier). The learner learns the Control Lyapunov Function (CLF), Koopman based observables, and the matrices constituting the Koopman bilinear system. The falsifier (SMT solver) is used to generate counterexamples that do no satisfy the Control Lyapunov conditions (or satisfy the falsification constraint). These counterexamples are added to the training set. The process is repeated until the SMT solver is used to generate any counterexamples.
