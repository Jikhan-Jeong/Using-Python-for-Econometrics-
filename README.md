# Using-Python-for-Econometrics-
Using Python for Econometrics

* Ref: http://www.upfie.net/downloads.html  
* Ref code: http://www.upfie.net/downloads13.html  
* statsmodels package: https://www.statsmodels.org/stable/index.html (for DiD and others)  
* linearmodels package: https://bashtage.github.io/linearmodels/ (for Panel and others)  

# Statmodels Jikhan-Defiend-Function for simplicity.
* Module is in Colab and keep update (not be posted in this github)  

import numpy as np  
import pandas as pd  
import statsmodels.formula.api as smf  

def data_summary(df):  
    print(df.shape)  
    print(df.columns)  
    return df.head(3)  

def stat_ols(formulas,df,subset=None, drop_cols=None):    
     reg = smf.ols(formulas, df,subset=None, drop_cols=None)    
     results = reg.fit()  
     print(results.summary())  
     return results  

(ex) stat_ols('lwage ~y85*(educ+female) + exper + I((exper**2)/100) + union', data)    
