# HOW MUCH ARE YOUR SKILLS WORTH ?
#### DATA JOB SALARY PREDICTION MODEL

## Project Strategy

**Objective : Build a model using mycareersfuture information that predicts job salary**

### Method: 
- **Scrape mycareersfuture titles, jobs descriptions, company names and salaries** (performed using scrapy - selector (this method worked best with mycareersfuture.com))

- **Scrape indeed.com titles, jobs descriptions, company names and salaries** (performed using Beautiful soup - selenium (this method worked best with indeed.com))

- **Perform data cleaning on both datasets**:
    - Cleaning dataframe: 
        - Lowercase all characters,remove non characters (text) and symbols (dollar values)
        - Remove jobs that do not meet criteria (i.e job has no description, title, company, or salary)
        
    - Extract job seniority (using keywords)
   
    - Group job titles by job type (using keywords)
    
    - Cleaning Job Salaries 
        - remove jobs with no salaries
        - Convert to numerical values, average salaries to new column
        - Transform salaries as monthly salaries
        - verify transformations
        - Rectify skew of salaries (log salary values)


- **NLP text transformation**
    - Generate stop words list (english stop words + common description words)
    - Perform 1) PorterStemmer or 2) WordNetLemmatizer (new columns)
    - Perform CountVectorizer + Tfif Transformer (TfidVectorizer) on descriptions, job title & companies
    - Dummify the job seniority
    - Make new dataframe with the transformed data
    
    
- **Exploratory Data Analysis**
    - Salaries according to Job Title
    - Salaries according to Seniority
    - PCA to visualize distribution of dataset.  
    
    
- **Model Selection for Linear Regression**
    - Base Model: LinearRegression
    - Regularization Models: Ridge, Lasso
    - Robust Models: HuberRegressor
   

- **Validate model using mycareersfuture test set**
    - Identify features with high coefs (positive and negative)
    
    
- **Predict salaries for indeed.com jobs**
    - Compare average salaries mycareersfuture by seniority/ job type versus predicted at indeed.com
    - Compare similar job at mycareersfuture versus indeed.com
