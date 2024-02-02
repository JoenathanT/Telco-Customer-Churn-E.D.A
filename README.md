# Notebook Instructions
## Dashboard build by tableu for the infomation you can click [Tableau_Dashboard]()
  1. Introduction
      > Hello, thankyou for your attention in this projects, My name is Jonathan Tuahta. the purpose of this project is to analyze the incidence of customer churn in telco companies and make strategy recommendations based on the company's customer data. in this project, i will process the existing data to identify the problems that occur in the company. then, with qualitative and quantitative analysis methods, i will look for problem solving to deal with the problems experienced by the company. with certain considerations such as the state of customers and companies, then i will provide suggestions that will become the company's strategy in dealing with problems about customer churn.

      > This project is a form of my practice in using technology software and websites such as python to process data, tableau for the process of visualizing data so that it can be presented, and kaggel as a website to get datasets.

  2. Problem Identification
      > Problem Identification using S.M.A.R.T.

        - Specify: Increase the customer loyalty of the company and increase the company's customers.

        - Measureable : maintain most of the long subscription by providing services that meet the needs of customers and provide benefits that can attract new customers.

        - Achievable: increase old customer satisfaction by providing services that each customer has registered, paying attention to customer information so that the company can find out the needs of customers.

        - Relevant: increasing customer satisfaction with each of our services can be an important factor in increasing company revenue, on the other hand the company name will be well known by the public so that it can attract potential customers.

        - Time Bound: the estimated goal can be set to be completed within two quarters of the work process with a record of the customer retention rate can increase by 50% and reduce the churn rate by 30%.

        *Problem Statement*

        `increase company revenue by increasing customer loyalty/customer retention by maximizing customer service, improving services that are considered unsatisfactory. this is done to retain most customers while attracting new customers. the company will target an increase in customer retention of 50% and reduce the churn rate by 30%.`


  3. Data Loading 
      > Dataset used in this project obtain from kaggle website. you can acces the [link_here](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

      > the dataset have 7043 lines with 20 column in total (16 columns object, 4 columns numerical ) with  details of dataset:

      | Column | Explanation |
       | ----- | --- |
       | Customer ID | contains each customer's unique value |
       | gender | whether the customer is male or female |
       | Senior Citizens | whether the customer belongs to senior society (old) (1 , 0) |
       | Partners | does the customer have a partner (Yes, No) |
       | Dependents | whether the customer has dependents or not (Yes, No) |
       | tenure | Number of months the customer has been with the company |
       | PhoneService | Whether the customer has telephone service or not (Yes, No) |
       | MultipleLines | Whether the customer has multiple lines or not (Yes, No, No phone service) |
       | InternetService | Customer internet service provider (DSL, Fiber optic, No) |
       | OnlineSecurity| Whether the customer has online security or not (Yes, No, No internet service) |
       | OnlineBackup | Whether the customer has online backup or not (Yes, No, No internet service) |
       | DeviceProtection | Whether the customer has device protection or not (Yes, No, No internet service) |
       | TechSupport | Whether the customer has technical support or not (Yes, No, No internet service) |
       | StreamingTV | Whether the customer has streaming TV or not (Yes, No, No internet service) |
       | StreamingMovies | bWhether the customer has streaming movies or not (Yes, No, No internet service) |
       | Contract | Customer contract term (Month to month, One year, Two years) |
       | PaperlessBilling | Whether the customer has paperless billing or not (Yes, No) |
       | PaymentMethod | Customer payment methods (Electronic check, Postal check, Bank transfer (automatic), Credit card (automatic)) |
       | MonthlyCharges | The amount charged to customers each month |
       | TotalCharges | Total amount charged to customers |
       | Churn | whether customers resubscribe (Yes, No) |


  4. Data Cleaning
      > The data displayed is data from the company and needs to be cleaned, for example there are columns that do not need to be used, we need to use ```dropna``` to delete data that is not needed, we also need to clean duplicate values in each table. ```drop_duplicates```, then we will also clean values that are not needed or if there are values that do not match the data column type use ```replace``` and after we check the values, we will check the data type in the column and If there is a need to change the data type we will use ```astype```.

      > `totalCharges` data type will transformed into float (before object) and i will drop customerID column because it is not useful for this project.

      > changing the column that only contain 2 values (yes and no) into boolean data(1 and 0).

  5. Analysis dan calculation.
      > 1. what factors influence customer interest in company?
       using P values, i will define each service in this dataset that will be customer interest to subscribe the company.
       for the calculation we will use:
       H0: the target column and churn column are not related
       H1: the target column and chutn column are related
       **note: for this, i ussualy using confidence percentage: 95%**

       >the result is:
       ![1](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/827d4c8e-7595-4f42-bd5e-cbf4f8f03ad0)
       ![2](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/c3261671-e402-4b4a-9474-20e4faecaa69)


       >It can be seen that the columns related to churn are ```SeniorCitizen, Partner, Dependents, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, Contract, PaperlessBilling, PaymentMethod ```

      > 2. Who is suitable for the services we provide? 
      for this question, i must seek for each customer preference in dataset. there is 3 column that describe for customer preference there are `customer_citizen`, `gender`, and `partner`. here is the plot details:
      ![3](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/ab79f039-2edc-4e8f-9a51-7ab5f0326be8)
      ![4](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/8d5b1d55-ea01-4fec-8c11-8c500cd412e8)
      ![5](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/0b45d60f-8e19-47f5-bf1b-1a1df0ad53c2)


      >From this analysis we can find out that our customers are mostly young people who still do not have dependents and have a partner.

      > 3. What is the average monthly expenditure & total expenditure for customers who are still subscribed?
      for this question, we must calclulate the customer that is still using the service. by the data that we gain, there are 921 customer who still using the service. we can calculate average cost in month and total average by separate customer that still use the service and customer who decice to leave the service. by using python to calculate we can gain some information that will be answer the question:
      ![7](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/ab873df8-54da-4d3d-ab1f-0c12ad1e28f1)


      > So it can be seen that the average monthly expenditure for customers is $58 per month and $2410 per year.

      > 4. What is the suitable price preference for the service based on customer expenditure?
      we can get the suitbale price by set the lower limit and upper limit for the monthly charge. from several calculations performed, a suitable upper and lower limit for each monthly expenditure was found. the lowest price limit suitable for each target customer is $64.05 per month and the maximum price limit suitable for each service is $65.50 per month. 

      ![8](https://github.com/JoenathanT/Telco-Customer-Churn-E.D.A/assets/91514437/8186aae1-177e-4d36-a81e-21340f8b3fa2)

      > It can be concluded that, we should set prices around $64-$65 for our services so that customers are not burdened with too expensive prices and the company does not suffer losses.

  6. Conclusion
      > It can be concluded from the description of the data above that PaymentMethod, Contract, TechSupport, DeviceProtection, OnlineBackup, OnlineSecurity, InternetService, Dependents, Partner, and SeniorCitizen have quite an influence on the company's churn rate. The need for steps such as improving services such as online security, online backup, device protection, tech support is enough to help companies reduce the churn rate.

      by the our data abaut customer preference, we can gain information that most of out customer is still in the financial development stage. Our customers have many financial responsibilities that are not balanced by their monthly income, on the other hand, the quality of the products we have does not match the customers' wishes. Therefore, we must adjust the quality of our products by providing product packages that suit customer desires with prices that need to be adjusted as well such as package bundle for the customer who wants to subscribe for only several service like internet service, online security, and online backup.

      most customers only last for 1 month, which indicates that customers are less than satisfied with the service provided to them. on the other hand, the prices given to customers are still quite high. Therefore, I recommend giving discounts to potential customers (this is necessary considering that companies cannot cut prices carelessly) and improving service so that they can be satisfied and want to subscribe longer