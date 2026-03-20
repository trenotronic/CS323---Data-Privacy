# CS 323 - Project 2: Privacy vs Utility 

## Project Overview
This project aims to expand our familiarity with k-anonymity though using a publicly availble dataset with microdata that has at minimum 10 attributes and 1,000 records. We used python as our coding language and the pandas library was heavily used in our code. 

**Contributors**:  
- Tren Meckel
- Tanvi Shegaonkar

## Project Structure
```
/
│── Project2_PrivUtility.ipynb       # Python file for cleaning, generalizing, and measuring utility for k=2,3,4
│── survey.csv                       # Original dataset. Should be in same directory

Everything below are generated files happening during our execution of the code:
│── survey_data_clean.csv        # This is the file that we used to clean up the original dataset.
│── anonymized_outputs               # Folder containing all 9 csv files for each value of k and l
    │── Final_Anon_Survery_k19_l2    # Anonymized records for k=19, l=2
    │── Final_Anon_Survery_k19_l2_5  # Anonymized records for k=19, l=2.5
    │── Final_Anon_Survery_k19_l3    # Anonymized records for k=19, l=3
    │── Final_Anon_Survery_k30_l2    # Anonymized records for k=19, l=2
    │── Final_Anon_Survery_k30_l2_5  # Anonymized records for k=19, l=2.5
    │── Final_Anon_Survery_k30_l3    # Anonymized records for k=19, l=3
    │── Final_Anon_Survery_k85_l2    # Anonymized records for k=19, l=2
    │── Final_Anon_Survery_k85_l2_5  # Anonymized records for k=19, l=2.5
    │── Final_Anon_Survery_k85_l3    # Anonymized records for k=19, l=3

│── Final_Anon_Survery_k19.csv       # Anonymized records for k=19
│── Final_Anon_Survery_k30.csv       # Anonymized records for k=30
│── Final_Anon_Survery_k85.csv       # Anonymized records for k=85
│── Not_Anon_Survery_k19.csv         # Not anonymized records for k=19
│── Not_Anon_Survery_k30.csv         # Not anonymized records for k=30
│── Not_Anon_Survery_k85.csv         # Not anonymized records for k= 85
│── kl_joint_results             # Show KL results of joint QIDs at all levels of k
```

## Instructions
# Ensure that the survey.csv is in the same file directory as Project2_PrivUtility.ipynb.
# Recommended to run Project2_PrivUtility.ipynb from top to bottom. If re-running individual cells, please restart kernel. 