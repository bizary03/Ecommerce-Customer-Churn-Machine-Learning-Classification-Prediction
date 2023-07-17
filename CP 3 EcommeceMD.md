# ***`Capstone Modul 3 Ecommerce Churn`***
___
# **Business Backgoruond and Problem**
## *`Background`*
Ecommerce has significantly growth in the past few years, fueled by advancements of technology and changing consumer preferences. It offers convenience, simplicity, wide product selection, competitive pricing, and personalized experiences. As the ecommerce trend and needs rocketing, it is quite a tough challange for all players to be able generate strategies to retain customers. Ecommerce churn rates have become a critical metric for businesses, influencing profitability and growth. Factors such as customer experience, product and promotional competition play significant role in customer retention. Analyzing churn patterns helps optimize strategies and mitigate revenue loss.

## *`Problem Statement`*
Nowadays in the era of ecommerce competition it is quite challenging to retain customer loyality due to the plenty variety of ecommerce platform. The method to keep them useing the platform sometimes will cost the company more. Considering there are also many variable to retain customer such as personalization, exelence customer experience and proactive retention campaigns, these methods will be time consuming and not really efficient if the customer identified as they are who already leaving the platform or we called it Churn.

## *`Goals`*
Based on the problem, company willing to know the best way to predict the customer whether they will churn or not, so the strategic team able to focus on them who predicted as potential churn and how to prevent them being churn. Furthermore the company able to capture what are the factors or variables that contribute the more to leads customer's churn, this will helps strategic team to avoid strategies that might not works on contributing to customer retention.

## *`Analytical Approach`*
This project will highlight on how ecommerce company be able to predict churn, using classificaation model that would capture customer's patern and predict wether they tend to be churn or not churn.

## *`Evaluation Metric`*
Target of this machine learning is to flag the churn, by that **churn** is the *positive* condition and **not churn** is the *negative*
- Class 1 : Churn
- Class 0 : Not Churn
<br>
<br>

False Positive : Predicted = churn, Actual = not churn<br>
**False Negative : Predicted = not churn, Actual = churn**

In this case False Negative con is leads to generate more risk to the company if we could not predict the actual chun, by that we consider to **reduce Fals Negative Rate** hence the metric evaluation needed is ***Recall***


## *`Data Prepocesing`*
Data prepocesing step is the step where we process cleaned data into the transformed data to be fitted for model testing.<br>
Initially we would like to do checking into each data type and value, hence we able to decide what to do in preprocessing.<br>
Let's look again to cleaned data to ensure the data is clean and to identify the data type.
Encode:
- Binary Encoder:
    - 'PreferedOrderCat'
- One Hot Encoder:
    - 'MaritalStatus'<br>

Scale:
- Robust Scaler:
    - 'Tenure', 'WarehouseToHome', 'NumberOfDeviceRegistered', 'SatisfactionScore', 'NumberOfAddress', 'DaySinceLastOrder', 'CashbackAmount'

We consider tu use Binary Encoder for 'PreferedOrderCat' due to this column has more than 5 category, and we can use One Hot Encoder for 'MaritalStatus' due to this column only contains 3 category. For Scaler we can use Robust Scaler because the data is not normally distributed.

# **Conclusion & Recommendation**
### *`Conclusion`*
- Use all columns as feature
- Preprocessing data using endocer and scaler
- Initial model testing resulting LightGBM and XGBoost as top two model
- Imbalance treatment resulting better score with LogReg and SVC as the best two model
- Tunnig result: SVC as best model and parameter to get best recall score of **98.11%**
- Confussion Matrix proves that we managed to reduce False Negative rate by **55.14%**
- Top 3 features contributing are: **CashbackAmount, Tenure and PreferedOrderCat**

### *`Recommendation`*
- To improve recall score better we need to consider adding feature that are more representing customer behaviors
- We can consider to use this model to do a future prediction of potential Churn customer, to be able set most efficient strategies to minimize the Churn rate
- Prioritizing on **CashbackAmount, Tenure and PreferedOrderCat** features to gather best customer retention plan in the future