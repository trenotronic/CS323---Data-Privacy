# CS 323 - Project 4: Differential Privacy

## Project Overview
This project extends **Project 3** by introducing a **fourth privacy-preserving method**—**Differential Privacy (DP)**—to compare against previous Secure Multiparty Computation (SMPC) approaches.  
The goal is to compute the **average of distributed integer values** while maintaining privacy, and to compare **runtime** and **accuracy** trade-offs across four methods:

1. **Non-private baseline** (direct mean)
2. **Paillier Encryption**
3. **Shamir’s Secret Sharing**
4. **Differential Privacy (Laplace mechanism)**

This project highlights how **cryptographic privacy** and **statistical privacy** differ in cost, scalability, and accuracy.

**Contributors**:  
- Tren Meckel (!)

## Project Structure
```
/ 
│── Project4.ipynb # # Main Python script with all code (Paillier, Shamir, DP, runtime + accuracy testing) 
│── READMEdp4.md # Project documentation (this file) 

Generated during code execution: 
│── project4_outputs              # Folder that has all the plots & csv file generated below
│── runtime_comparison.png/pdf    # Log-scale runtime comparison graph 
│── accuracy_comparison.png/pdf   # Differential Privacy accuracy (MAE) plot
│── phase_comparison.pdf          # Paillier vs. Shamir phase timing breakdown
│── results_dp.csv                # table of all results
\
```

Experiment Configuration

The experiments were run for the following number of parties (n):

n_values = [10, 50, 100, 250, 500]


The threshold for Shamir’s Secret Sharing was set to:

threshold = n // 2


Differential Privacy parameter: 

epsilon = 1.0

## Instructions
# Ensure Project4.ipynb is in your working directory.
# Install dependencies (recommended via pip):
##   pip install numpy matplotlib phe
#Run the experiment:
##   python Project4.ipynb
#This will execute all tests for each n value and generate runtime plots and PDF output.
