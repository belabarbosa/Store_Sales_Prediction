# Sales Prediction for Rossmann Drugstore Chain

<p align="center">
  <img src="https://user-images.githubusercontent.com/100521949/233401462-7e93b6e5-b0fb-4fb5-bc99-6f7bcdcc011d.jpg" />
</p>

The objectives of this project are as follows:

- Conduct an exploratory data analysis on the sales data available in the dataset.

- Discover actionable insights that can be used to improve the performance of the company.

- Develop and train a Machine Learning model that can accurately predict sales for the next six weeks from each store in the pharmacy chain.

- Deploy the solution on the cloud and create a bot that can be accessed by end users from various devices.

Overall, the goal of this project is to leverage data and machine learning to enhance the performance of the pharmacy chain and make accurate predictions about the sales numbers.


## 1. Business Problem

Dirk Rossmann GmbH, commonly known as Rossmann, is a German drugstore chain that operates in various European countries, including Germany, Poland, Hungary, Czech Republic, Turkey, and Albania. It is the second-largest drugstore chain in Germany, with around 56,200 employees and more than 4000 stores. 

The company offers a wide range of products, including personal care items, cosmetics, household supplies, baby products, and healthcare items, among others and is known for its competitive prices and its focus on customer satisfaction, winning several awards for its commitment to sustainability and social responsibility.

The CFO needs to determine how much can be invested in renovating each store, and has requested a sales forecast project to help inform these decisions. The Data Scientist has been tasked with developing a model that can accurately forecast sales for each store over the next six weeks.

To facilitate easy access to these predictions, a Telegram bot has been developed. The bot will provide users with sales forecasts for a specific store upon request.


## 2. Business Assumptions

- Since we are studying the sales phenomenon, the days that the stores were closed and/or the sales were equal to 0 were not considered.

- If competition_distance is not available, it means that there is no competition or the closest competitor is so far away that it was disregarded. To represent this, a distance much greater than the greatest distance found in the dataset was placed.

- If competition_open_since_month is not available, the sale date was used in that column because for the feature engineering stage, there are some variables that we derive from time that are very important to represent the behavior.

- For competition_open_since_year the same logic as competition_open_since_month was applied. 

- If promo2_since_week is not available, it means that the store has decided not to extend its participation in this promotion. 

- For promo2_since_year the same logic as promo2_since_week.


## 3. Solution Strategy

### **Step 1: Data description** 
The goal in this step is to see the quality and dimensions of the data and understand some aspects of the business. To achieve this, I handled missing values, modified certain data types, and utilized descriptive statistics to explore the numerical and categorical attributes.

### **Step 2: Feature Engineering**
For this step, I utilized the mind map below with the phenomenon under study at the center, surrounded by the agents that affect it and their respectives attributes. The purpose was to formulate a hypothesis that would serve as a guiding principle for the project. These hypotheses are valuable in defining the scope of the project and determining which features are essential to pursue further.

<p align="center">
  <img src="https://user-images.githubusercontent.com/100521949/233451690-73207180-bd4a-490c-8381-2046bb3f5693.png" />
</p>

> 📘 Note
>
> To create the mind map for this project, I developed the agents and their attributes based on my understanding of the phenomenon. In a company setting, this map is usually generated through a collaborative brainstorming session involving all stakeholders in the project.


### **Step 3: Data Filtering**
In this step, I selectively filtered out rows and columns from the dataset that were deemed irrelevant to the modeling process or fell outside the scope of the business. The objective was to create a more compact dataset, focused solely on the information that was essential for the task at hand.

### **Step 4: Exploratory Data Analysis (EDA)**
The EDA step has the goal to gain a deeper understanding of the business, generate insights, and explore correlations between the available features through univariate, bivariate, and multivariate analysis. It helps to identify which variables are most relevant for the model learning and improve the overall effectiveness of the project.

> 📘 Note
>
> This step is crucial and can deliver substantial benefits to the organization. A well-executed Exploratory Data Analysis (EDA) can resolve numerous issues within the organization, without requiring the creation of a machine learning model. For Business Intelligence Analysts and Data Analysts, the EDA phase is often the concluding phase of their data science projects.

### **Step 5: Data Preparation**


### **Step 6: Feature Selection**

### **Step 7: Machine Learning Modeling**

### **Step 8: Hyper Parameter Fine Tuning**

### **Step 9: Model Evaluation**

### **Step 10: Deployment**


## 4. Top Insights

### Insight 01
While the initial hypothesis suggests that stores with larger assortments will sell more, the analysis reveals that the opposite is true: stores with greater assortments actually sell less.

This revised version clarifies the contrast between the expected outcome (more sales with more products) and the actual outcome (less sales with more products).

![image](https://user-images.githubusercontent.com/100521949/233478003-a0b80c0d-c431-4b60-a413-7b1c52c1a244.png)

### Insight 02
Stores with closest competitors sell more.

![image](https://user-images.githubusercontent.com/100521949/233478164-60e64585-e80c-4093-a253-25ac474f6fe4.png)

### Insight 03
Stores with competitors for a longer time sell less.

![image](https://user-images.githubusercontent.com/100521949/233478269-8dbe9be3-f4e5-422b-b300-a10fc20318f0.png)

### Insight 04
Stores that joined the extended period of promotion sell less.

![image](https://user-images.githubusercontent.com/100521949/233478767-275d8b65-13cf-496b-bf87-c9a1ccf0a1e0.png)




## 5. Machine Learning Models Applied

## 6. Machine Learning Performance

### Single performance
![image](https://user-images.githubusercontent.com/100521949/233423240-ebe7a310-7153-42b8-9712-1d43c6202d86.png)


### Real performance - Cross Validation
![image](https://user-images.githubusercontent.com/100521949/233425050-d5e1570d-8179-4f25-9f12-4e4ff49a934e.png)



## 7. Business Results

## 8. Conclusion

## 9. Lessons Learned

## 10. Next Steps

The CRISP methodology is designed to deliver prompt solutions for businesses. Therefore, it is essential to assess the efficacy of the solution at the end of each cycle. With input from all stakeholders, it is important to determine whether to proceed with a new cycle or shift focus to a new project.

If the decision is to move forward with a new cycle, here are some recommended next steps:

- Separate validation and test datasets before the EDA to prevent data leakage.
- Explore better ways to address missing values. 
- Generate new business hypotheses.
- Collect more data in order to improve the model and also to create new features.
- Test alternatives machine learning models.
- Improve messages on Telegram bot and include a chart or other visualization tool to enhance decision making.
- Investigate why the model did not perform well for certain stores and address any issues accordingly.
- As there is a strong correlation between the number of customers in the stores and sales, it would be beneficial to work on a project to predict the number of customers and include this variable in the model.
