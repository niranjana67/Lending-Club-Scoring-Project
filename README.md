# Lending-Club-Scoring-Project

This repository contains the ETL (Extract, Transform, Load) workflows for the Lending Club Project, designed to generate final scoring metrics from key datasets:
- Customers
- Loans
- Loan Repayments
- Loan Defaulters
  
Key Objectives
The project focuses on building a robust data pipeline to ensure accurate scoring through the following steps:
- Data Cleaning – High-level cleansing to remove inconsistencies and prepare raw data.
- Data Transformation – Applying structured transformations for standardized processing.
- Bad Data Identification – Detecting anomalies and invalid records.
- Bad Data Segregation – Isolating problematic data for further review.
- Final Scoring – Generating comprehensive scoring outputs for customer and loan evaluation

### Table required for calculate loan score
1. customers_new -> home_ownership, grade, high_credit_limit
2. loans -> monthly_installment, load_status, funded_amount
3. loan_repayment -> last_payment, total_payment_received
4. loan_defaulter_delinq_new -> delinq_2_yrs
5. loan_defaulter_public_rec_new -> public_rec, pub_bankruptcies, inq_last_6mnths

### Loan Criteria
1. Payment history (ph) -> 20%  (last_payment, total_payment_amount)
2. Defaulter history (dh) -> 45% (delinq_2yrs,pub_rec, pub_bankruptices,inq_last_6mnths)
3. Financial health data (fh) -> 35% (home_ownership, loan_status, funded_amount, grade, subgrade)
