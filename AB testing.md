```python
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt 
from scipy.stats import chi2_contingency , chi2
```


```python
campaign_data = pd.read_excel(r"C:\Users\CharlesQ\Downloads\grocery_database (1).xlsx", sheet_name = "campaign_data")
```


```python
campaign_data.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>customer_id</th>
      <th>campaign_name</th>
      <th>campaign_date</th>
      <th>mailer_type</th>
      <th>signup_flag</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>74</td>
      <td>delivery_club</td>
      <td>2020-07-01</td>
      <td>Mailer1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>524</td>
      <td>delivery_club</td>
      <td>2020-07-01</td>
      <td>Mailer1</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>607</td>
      <td>delivery_club</td>
      <td>2020-07-01</td>
      <td>Mailer2</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>343</td>
      <td>delivery_club</td>
      <td>2020-07-01</td>
      <td>Mailer1</td>
      <td>0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>322</td>
      <td>delivery_club</td>
      <td>2020-07-01</td>
      <td>Mailer2</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>




```python
## fILTER DATA filter out control group 

campaign_data = campaign_data.loc[campaign_data['mailer_type'] != "Control"]
    

```


```python
## summarise to get observed values 

observed_value = pd.crosstab(campaign_data['mailer_type'], campaign_data['signup_flag']).values 
```


```python
observed_value
```




    array([[252, 123],
           [209, 127]])




```python
mailer1_signup_rate = 123/(252+123)
mailer2_signup_rate = 127/(209+127)
print(round(mailer1_signup_rate *100,2))
print(round(mailer2_signup_rate *100,2))
```

    32.8
    37.8
    


```python
## Setting up hypothesis test

null_hypothesis = "There is no relationship between mailer type and signuprate. They are independent"
alternative_hypothesis = "There is a relationship between mailer type and signuprate. They are not independent"
acceptance_criteria = 0.05 
```


```python
## calculating expected chi squred statistics and contingency 

chi2_statistics, p_value, dof, expected_values = chi2_contingency(observed_value, correction = False)
print(chi2_statistics, p_value)
```

    1.9414468614812481 0.16351152223398197
    


```python
## Finding critical value for test 

critical_value = chi2.ppf(1 - acceptance_criteria, dof)
print(critical_value)
```

    3.841458820694124
    


```python
##Print results for chi squred statistics 
if p_value <= acceptance_criteria:
    print(
        f"As the p-value ({p_value:.3f}) is less than or equal to the significance level "
        f"({acceptance_criteria:.3f}), we reject the null hypothesis and conclude that there "
        f"is a statistically significant relationship between the variables."
    )
else:
    print(
        f"As the p-value ({p_value:.3f}) is greater than the significance level "
        f"({acceptance_criteria:.3f}), we fail to reject the null hypothesis and conclude that "
        f"there is insufficient evidence of a statistically significant relationship between the variables."
    )
```

    As the p-value (0.164) is greater than the significance level (0.050), we fail to reject the null hypothesis and conclude that there is insufficient evidence of a statistically significant relationship between the variables.
    


```python
##Print results for p value
if p_value <= acceptance_criteria:
    print(
        f"As the p-value ({p_value:.3f}) is less than or equal to the acceptance criteria "
        f"({acceptance_criteria:.3f}), we reject the null hypothesis and conclude that "
        f"{alternative_hypothesis}."
    )
else:
    print(
        f"As the p-value ({p_value:.3f}) is greater than the acceptance criteria "
        f"({acceptance_criteria:.3f}), we fail to reject the null hypothesis and conclude "
        f"that there is insufficient evidence to support {alternative_hypothesis}.")
```

    As the p-value (0.164) is greater than the acceptance criteria (0.050), we fail to reject the null hypothesis and conclude that there is insufficient evidence to support There is a relationship between mailer type and signuprate. They are not independent.
    


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
