# CS 323 - Project 1: Anonymity

## Project Overview
This project aims to expand our familiarity with k-anonymity though using a publicly availble dataset with microdata that has at minimum 10 attributes and 1,000 records. We used python as our coding language and the pandas class was heavily used in our code. 

**Contributors**:  
- Tren Meckel
- Tanvi Shegaonkar

## Project Structure
```
/
│── Project1_Anonymity.ipynb    # Python file for cleaning, generalizing, and measuring utility for k=2,3,4
│── survey.csv                  # Original dataset. Should be in same directory 

    Everything below are generated files happening during our execution of the code:
│── survey_data_clean.csv       # This is the file that we used to clean up the original dataset.
│── Final_Anon_Survery_k2       # Anonymized records for k-anonmity at level 2
│── Final_Anon_Survery_k3       # Anonymized records for k-anonmity at level 3
│── Final_Anon_Survery_k4       # Anonymized records for k-anonmity at level 4     
│── Not_Anon_Survey_k2          # Show records not anonymized at level 2 (used for checking)   
│── Not_Anon_Survey_k3          # Show records not anonymized at level 3 (used for checking)           
│── Not_Anon_Survey_k4          # Show records not anonymized at level 4 (used for checking)         
│── kl_results_k2               # Show KL results of individual QIDs at level 2      
│── kl_results_k3               # Show KL results of individual QIDs at level 3
│── kl_results_k4               # Show KL results of individual QIDs at level 4
│── kl_joint_results            # Show KL results of joint QIDs at all levels of k
```

## Instructions
# Ensure that the survey.csv is in the same file directory as Project1_Anonymity.ipynb.
# Recommended to run Project1_Anonymity.ipynb from top to bottom. If re-running individual cells, please restart kernel. 