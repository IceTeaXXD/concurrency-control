# Concurrency Control Protocl
> Tugas Besar 1 Manajemen Basis Data - Concurrency Control

# About
Concurrency Control Protocol is a program that simulates concurrency control in database management system. This program includes 3 concurrency control protocol, which are: Two Phase Locking (2PL), Optimistic Concurrency Control (OCC), and Multiversion Timestamp Ordering (MVTO).

# Contributors

| NIM | Nama |
| --- | --- |
| 13521008 | Jason Rivalino |
| 13521010 | Muhamad Salman Hakim Alfarisi |
| 13521024 | Ahmad Nadil |
| 13521026 | Kartini Copa |

# How to Run
Easy way: open the website [here](https://concurrency-control.vercel.app/)

OR, to run the website locally:

1. Clone this repository
2. Run the frontend
    ```bash
    cd src/concurrency-control-fe
    yarn
    yarn dev
    ```
3. Run the backend
    ```bash
    cd src/concurrency-control-be
    py index.py
    ```

OR, to run only the backend:
```bash
python src/concurrency-control-be/ <TwoPhaseLocking / OCC / MVCC>.py
```

# How to Use
Input a sequence of transactions, below are the examples:
```bash
R1(X);R2(X);R1(Y);C1;C2
R1(A);R2(B);W1(A);R1(B);W3(A);W4(B);W2(B);R1(C);C1;C2;C3;C4
R1(A);W2(A);R2(A);R3(A);W1(A);C1;C2;C3
R1(X);W2(X);W2(Y);W3(Y);W1(X);C1;C2;C3
R1(X);R2(Y);W1(Y);W1(X);W1(X);C1;C2
R1(X);R2(X);W1(X);W2(X);W3(X);C1;C2;C3
R1(X);R1(X);R2(X);R3(X);W1(X);W2(X);W3(X);C1;C2;C3
R1(X);R2(X);W2(X);C1;C2
R1(X);R2(X);W1(X);C1;C2
R1(X);R2(X);R3(X);W1(X);W2(X);W3(X);C1;C2;C3
```