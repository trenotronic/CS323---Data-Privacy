# CS 323 - Project 6: Privacy-Preserving Machine Learning

## Project Overview
This project implements a secure-style decision tree evaluation workflow inspired by secure multiparty computation (SMPC).
--> The goal is to simulate how a model owner and a data owner could jointly evaluate a decision tree without revealing sensitive information, using simplified secure comparison and oblivious branching operations.

**Contributors** 
- Tren Meckel
- Kushal Sigdel

## Project Structure
```
/
│── Project6.ipynb              # Main notebook containing all code, documentation, and results
│── drug_consumption.csv        # Preprocessed dataset from the UCI Drug Consumption (Quantified) dataset
│── secure_tree_plot.png        # Saved visualization of the decision tree
│── README.md                   # Documentation and project details (this file!)

```

## Running the code
To run the notebook:

1) Make sure Project6.ipynb and drug_consumption.csv are in the same directory.
2) Open the notebook with any enviroment that supports .ipynb files (like Jupyter or VScode)
3) Run each cell of notebook, top to bottom

The notebook performs the following steps:

- Loads and preprocesses the Drug Consumption (Quantified) dataset
- Trains a standard decision tree classifier
- Converts the trained model into a custom TreeNode structure
- Defines secure-style operations for secure comparison and oblivious branching
- Performs secure decision tree evaluation on individual samples and the entire dataset
- Computes secure inference accuracy
- Visualizes the trained decision tree

## Relevant Information for running with alternative inputs
The notebook accepts any dataset that follows the same structure as the Drug Consumption dataset (32 columns: 1 ID field, 12 continuous features, and 19 drug usage columns in CL0–CL6 format).

To evaluate a different drug as the target variable, simply change the target_drug argument in:
    X, y = load_drug_data(target_drug="Cannabis")
to for example:
    X, y = load_drug_data(target_drug="Cocaine")
    
You may also modify the decision tree parameters (if you want..):
    clf = train_decision_tree(max_depth=5, min_samples_leaf=20)

This project simulates the structure of secure decision tree evaluation but does not implement real cryptographic secure multiparty computation (SMPC) operations. This project supports multiple types of input data, fulfilling the assignment requirement. First, the code can load any CSV file that follows the same 32-column structure as the Drug Consumption dataset by changing the path= argument in load_drug_data(). Second, the user can choose different classification targets by setting target_drug= to any of the 19 drug-use columns (e.g., Cannabis, Cocaine, Heroin, LSD), allowing the same workflow to train and evaluate different models. Third, the secure evaluation function works for multiple instances: it can evaluate a single feature vector, all samples in the dataset, or any subset of rows. Finally, the secure_eval() function accepts any correctly formatted list of 12 continuous feature values, meaning the model can securely evaluate arbitrary input vectors—not only those loaded from the dataset. Together, these features demonstrate the program’s ability to process multiple inputs in a variety of ways, as much as can be done with Secure Decision Tree evaluation with SMPC. 

## Parameters Affecting Privacy, Usability, and Efficiency (Analysis)
Several settings in this project affect how the program behaves, especially in terms of privacy, accuracy, and speed. The most important parameters are the tree depth (max_depth) and the minimum samples per leaf (min_samples_leaf). A deeper tree means the model can split the data more and possibly make more accurate predictions. However, deeper trees also require more secure-style comparisons during evaluation, which would be slower and more expensive in a real SMPC system. On the other hand, smaller trees are faster and require fewer secure steps, but may lose accuracy. In a real SMPC implementation, these parameters don’t change the theoretical privacy guarantee (the protocol either is or isn’t secure), but they change how many secure operations are needed and therefore the practical feasibility of running a privacy-preserving protocol. 

The choice of which drug is used as the target label also matters. Different drugs have different class distributions, which affects how easily the model can learn patterns and how accurate predictions will be. Even though this project uses simplified “secure-style” operations instead of full cryptography, these parameters show the usual tradeoff in privacy-preserving ML systems: more complex models give better accuracy, but require more secure computation, while simpler models run faster but may be less accurate. 
