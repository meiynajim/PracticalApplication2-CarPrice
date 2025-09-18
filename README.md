**Business Goal:** Identify key drivers for used car prices to recommendate what consumers value in a used car to a car dealership client

**Data Problem to Solve:** Explore data to identify the relevant data insights to achieve the business goal

**Data Provided:**

   - number of records: 426,880
     
   - number of columns: 18 columns with price, vehicle attributes, and geographical variables

**Data Analytics Process Summary:**
   
**Section 1. Data Understanding**


##### Step 1. Initial Data Review

##### Step 2. Project Data Scope based on the initial data review in Step 1:
- 1. Records with `price < $100 & year <=1990` are not meaningful for this business goal so will be dropped
- 2. Records with `odometer`<= 0 & `odometer` > 500000 are not meaningful for this business goal so will be dropped
- 3. Variables with a `missing % >= 70%` could be too time consuming to work with so `Size` will be dropped for this iteration of analysis
- 4. Categorical variables have too many levels will be dropped for now: 
     - `Model` (29649 levels) will be dropped for this iteration of analysis
- 5. Geographical variable `Regions` (404 levels) will be dropped for this iteration of analysis (`State` will be used instead) 
- 6. `VIN` could be decoded and cleaned up to obtain accurate vehicle attributes but it is out of scope of this iteration of analysis 
- 7. `id` will be dropped from analysis
 
##### Step 3. Data Cleaning: drop records based on the project data scope in Step 2

 - 1. Assuming `price` needs to be >=50, otherwise, likely a gift & <=100K, otherwise, too expensive to regular customers / rare customized unique car
 - 2. Assuming `odometer` needs to be > 0 & `odometer` < 500000
   3. `Size`: too much missing data over 70% so drop
 - 4. `Model`: too many levels/unique values 29649 - drop for this analysis
 - 5. `Region`: too many levels (404) / unique values - drop for this analysis
 - 6. `VIN`: not usable directly - drop for now (can do decode VIN later when time allows)
 - 7. `id`: no meaning

##### Step 4. Exploratory Data Analysis

##### Step 5. Feature Review

##### Step 6. Data Pre-processing & Feature Engineering

   1. Create vehicle_age, mileage_per_year, and ind_luxury
   2. Target Mean Binning or Mean-based Category Grouping - This approach:
       - Reduces cardinality
       - Helps eliminate noise from rare or redundant levels
       - Makes encoding + modeling faster and more interpretable

**Section 2. Data Preparing**

 - Step 1. Data Cleaning

       - Target & Numerical Varialbes: Dropping records without meaningful prices & Dealing with outliers
      
 - Step 2. Missing Data Imputation

 - Step 3. Feature Review
    
 - Step 4. Feature Engineering & Data Pre-processing

       - Unsupervised learning PCA to reduce data dimentionality: better results but less interpretability)
   
**Section 3. Modeling**

           - Supervised learning to build price predictive model
           
           - Feature Importance Selection vs Including PCA (as a comparison option)
           
**Section 4. Evaluation**

**Section 5. Deployment**
In conclusion, this project focused on predicting used car prices using a structured approach based on the CRISP-DM framework. We started with understanding business objectives and data collection, followed by thorough data preparation, modeling, evaluation, and deployment phases. Here's a summary of our findings and actionable insights:

#### 1. Preliminary Data Insight Summary
![image.png](attachment:66536cc0-2b05-400b-98a9-ce059e2fe85a.png)

Notes: 
 - 1. More feature engineering for `type`, `state`, `title`, `drive`, `condition`, `transmission`, etc.
 - 2. Since one of the critical variables, such as `model`, was not good to use direcctly, some of coefficients might show less desirable values
 - 3. Luxury_Ind inlcluding brands: 'ferrari','audi', 'bmw', 'mercedesbenz', 'lexus', 'porsche', 'jaguar', 'land rover', 'tesla', 'acura', 'infiniti','lincoln','cadillac'. We should be able to modify the list

#### 2. Actionable Insights

By leveraging these insights, our business can improve its competitive edge, drive revenue growth, and enhance customer satisfaction.

- **Optimize Pricing Strategy:**
    - Implement dynamic pricing based on mileage, vehicle age, and demand to maximize profits.
    - Monitor regional trends and adjust prices to align with local market conditions.

- **Continuous Model Refinement:**
    - Regularly update the predictive model with new data to maintain accuracy.
    - Incorporate user feedback and market insights to enhance model performance.


#### 3. Analytics Tool
 - **Developing a pricing dashboard**

**Section 6. Next Steps**

1. PCA: add some visualization to be more interpretable
2. DBSCAN could be utilized to identify outliers
3. Time series: price vs year
4. Model: need to work on data cleaning and feature engineering
5. VIN: could be decoded to impute missing values and have more accurate vehicle attributes
6. More Feature Engineering
7. More Model Tuning
8. Analytics Tool Development, such as a interactive pricing dashboard 

           
