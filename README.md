# Notebook Instructions
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
       | ownership | Number of months the customer has been with the company |
       | Telephone Services | Whether the customer has telephone service or not (Yes, No) |
       | Many Lines | Whether the customer has multiple lines or not (Yes, No, No phone service) |
       | Internet Services | Customer internet service provider (DSL, Fiber optic, No) |
       | Online Security| Whether the customer has online security or not (Yes, No, No internet service) |
       | Online Backup | Whether the customer has online backup or not (Yes, No, No internet service) |
       | Device Protection | Whether the customer has device protection or not (Yes, No, No internet service) |
       | Technical Support | Whether the customer has technical support or not (Yes, No, No internet service) |
       | StreamTV | Whether the customer has streaming TV or not (Yes, No, No internet service) |
       | StreamingFilms | bWhether the customer has streaming movies or not (Yes, No, No internet service) |
       | Contract | Customer contract term (Month to month, One year, Two years) |
       | Paperless Billing | Whether the customer has paperless billing or not (Yes, No) |
       | Payment Method | Customer payment methods (Electronic check, Postal check, Bank transfer (automatic), Credit card (automatic)) |
       | Monthly Fees | The amount charged to customers each month |
       | Total Cost | Total amount charged to customers |
       | Play | whether customers resubscribe (Yes, No) |


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
       ![no1](..\Telco-Customer-Churn-E.D.A\img\1.png)
       ![no2](..\Telco-Customer-Churn-E.D.A\img\2.png)

       >It can be seen that the columns related to churn are ```SeniorCitizen, Partner, Dependents, MultipleLines, InternetService, OnlineSecurity, OnlineBackup, DeviceProtection, TechSupport, StreamingTV, StreamingMovies, Contract, PaperlessBilling, PaymentMethod ```

      > 2. Who is suitable for the services we provide? 
      for this question, i must seek for each customer preference in dataset. there is 3 column that describe for customer preference there are `customer_citizen`, `gender`, and `partner`. here is the plot details:
      ![no3](..\Telco-Customer-Churn-E.D.A\img\3.png)
      ![no4](..\Telco-Customer-Churn-E.D.A\img\4.png)
      ![no5](..\Telco-Customer-Churn-E.D.A\img\5.png)

      >From this analysis we can find out that our customers are mostly young people who still do not have dependents and have a partner.

      > 3. What is the average monthly expenditure & total expenditure for customers who are still subscribed?
      for this question, we must calclulate the customer that is still using the service. by the data that we gain, there are 921 customer who still using the service. we can calculate average cost in month and total average by separate customer that still use the service and customer who decice to leave the service. by using python to calculate we can gain some information that will be answer the question:
      ![no7](..\Telco-Customer-Churn-E.D.A\img\7.png)

      > So it can be seen that the average monthly expenditure for customers is $58 per month and $2410 per year.

      > 4. What is the suitable price preference for the service based on customer expenditure?
      





  6. Pengambilan Kesimpulan
      > Pada bab terakhir ini, **harus berisi** kesimpulan yang mencerminkan solusi/rekomendasi/jawaban atas permasalahan yang diangkat serta menarik benang merah dari seluruh analisis dan perhitungan secara singkat, jelas, dan padat.

3. Simpan notebook dengan judul h8dsft_Milestone1_<nama-student>.ipynb, misal h8dsft_Milestone1_raka_ardhi.ipynb

## Dashboard

1. Dashboard build by tableu for the infomation you can clik [Tableau_Dashboard]()
3. Untuk bagian Visualisasi :
  - Minimal ada 4 figure/visualisasi data yang ditampilkan dalam halaman `Visualisasi` yang sesuai dengan yang dibuat pada Notebook.
  - Minimal ada 1 interactivity pada dashboard
  - Tidak perlu menulis insightnya, dashboard visualisasi sejatinya hanya kumpulan visualisasi data
  - Apabila jenis plot pada dashboard dengan di Python berbeda, dari segi jenis dan hasil, tidak masalah jika lampirkan plot dari dashboard ke notebook dan tetap tampilkan data yang sudah dipreprocess pada notebook.
4. Untuk bagian Statistical Analysis:
  - Tulis proses analisis statistik deskriptif dan inferential yang dilakukan di notebook dari masalah yang diangkat hingga kesimpulan dari hasil analisis statistik.

5. Presentasikan dashboard yang telah dibuat pada P1W1D4PM.

---

