# CS 323 - Project 3: Secret Sharing 

## Project Overview
This project explores Secure Multiparty Computation (SMPC) through two privacy-preserving approaches: Paillier Encryption and Shamir’s Secret Sharing, compared against a non-private baseline.
The goal was to compute the average of distributed integer values while maintaining privacy, and to compare the runtime performance of each method as the number of parties increased.
**Contributors**:  
- Tren Meckel (!)

## Project Structure
```
/ 
│── Project3.py # Main Python file containing all code (Paillier, Shamir, and runtime testing) 
│── README.md # Project documentation (this file) 

Generated during code execution: 
│── (Note: all pngs also have pdfs as well)
│── runtime_comparison_linear.png # Linear-scale runtime comparison graph 
│── runtime_comparison_log.png    # Log-scale runtime comparison graph 
│── runtime_bar_fixed_n.png       # Bar chart comparison for n = 500 
│── paillier_runtime.png          # Scale of paillier by itself
│── shamir_runtime.png            # Scale of shamir by itself
\
```

Experiment Configuration

The experiments were run for the following number of parties (n):

n_values = [10, 50, 100, 250, 500]


The threshold for Shamir’s Secret Sharing was set to:

threshold = n // 2


Each party held one random integer value between 1 and 100.

## Instructions
# Ensure Project3.ipynb is in your working directory.
# Install dependencies (recommended via pip):
##   pip install numpy matplotlib phe
#Run the experiment:
##   python Project3.ipynb
#This will execute all tests for each n value and generate runtime plots and PDF output.
