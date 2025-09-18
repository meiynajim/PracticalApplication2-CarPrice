**1. Business Goal:** Identify key drivers for used car prices to recommendate what consumers value in a used car to a car dealership client

**2. Data Problem to Solve:** Explore data to identify the relevant data insights to achieve the business goal

**3. Data Provided:**

   - number of records: 426,880
     
   - number of columns: 18 columns with price, vehicle attributes, and geographical variables

**4. Data Analytics Process Summary:**
   
**Section 1. Data Understanding**

Step 1. Initial Data Review: there are some missing across most of variables; no duplicates; some records without business meaning need to be dropped
        
Step 2. Project Data Scope: Based on the initial data review, the records with price > $50 & year >=1980 are determined to be meaningful for the business goal

Step 3. Data Cleaning: 

        - Target: Dropping records without meaningful price; Dealing with outliers
        
        - Numerical Variables
        
        - Categorical Variables
        
Step 4. Missing Data Imputation

Step 5. Exploratory Data Analysis

Step 6. Feature Engineering & Data Pre-processing
       - Unsupervised learning PCA to reduce data dimentionality
       
**Section 2. Modeling**

           - Supervised learning to build price predictive model
           
           - Feature Importance Selection vs Including PCA (as a comparison)
           
**Section 3. Evaluation**

**Section 4. Deployment**
             - An interactive pricing dashboard would be sufficient for dealer to use for price quotes

**Section 5. Next Steps**

           - PCA: performed but not implemented as less interpretable
           
           - DBSCAN could be utilized to identify outliers
           
           - Time series: price vs year
           
           - VIN: could be decoded to impute missing values and have more accurate vehicle attributes
           
           - More Feature Engineering
           
           - Analytics Tool Development, such as a interactive pricing dashboard

           
