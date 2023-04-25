# Sales Prediction for Rossmann Drugstore Chain

<p align="center">
  <img src="https://user-images.githubusercontent.com/100521949/233401462-7e93b6e5-b0fb-4fb5-bc99-6f7bcdcc011d.jpg" />
</p>

The objectives of this project are as follows:

- **Conduct an exploratory data analysis on the sales data** available in the dataset.

- **Discover actionable insights** that can be used to improve the performance of the company.

- **Develop and train a Machine Learning model that can accurately predict sales** for the next six weeks from each store in the pharmacy chain.

- **Deploy the solution on the cloud** and create a bot that can be accessed by end users from various devices.

Overall, the goal of this project is to leverage data and machine learning to enhance the performance of the pharmacy chain and make accurate predictions about the sales numbers.


## 1. Business Problem

Dirk Rossmann GmbH, commonly known as Rossmann, is a German drugstore chain that operates in various European countries, including Germany, Poland, Hungary, Czech Republic, Turkey, and Albania. It is the second-largest drugstore chain in Germany, with around 56,200 employees and more than 4000 stores. 

The company offers a wide range of products, including personal care items, cosmetics, household supplies, baby products, and healthcare items, among others and is known for its competitive prices and its focus on customer satisfaction, winning several awards for its commitment to sustainability and social responsibility.

**The CFO needs to determine how much can be invested in renovating each store, and has requested a sales forecast project to help inform these decisions. The Data Scientist has been tasked with developing a model that can accurately forecast sales for each store over the next six weeks.**

To facilitate easy access to these predictions, a Telegram bot has been developed. The bot will provide users with sales forecasts for a specific store upon request.


## 2. Business Assumptions

- Since we are studying the sales phenomenon, the days that the stores were closed and/or the sales were equal to 0 were not considered.

- If ```competition_distance``` is not available, it means that there is no competition or the closest competitor is so far away that it was disregarded. To represent this, a distance much greater than the greatest distance found in the dataset was placed.

- If ```competition_open_since_month``` is not available, the sale date was used in that column because for the feature engineering stage, there are some variables that we derive from time that are very important to represent the behavior.

- For ```competition_open_since_year``` the same logic as ```competition_open_since_month``` was applied. 

- If ```promo2_since_week``` is not available, it means that the store has decided not to extend its participation in this promotion. 

- For ```promo2_since_year``` the same logic as ```promo2_since_week```.

## 3. Planning

With the goal to deliver a fast yet effective solution to the business problem, while making sure the tools and data available would make the project viable, the project was developed using the Cross-Industry Standard Process for Data Science (CRISP-DS) methodology as shown below:

<p align="center">
  <img src="https://user-images.githubusercontent.com/100521949/233659506-954780d0-fb20-40ff-9b72-e4fc8b3d8d39.png" />
</p>

## 4. Solution Strategy

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
Machine learning algorithms typically perform better with numerical data that has been scaled to the same range. By effectively modeling variables, the algorithm can learn the true importance of each variable without introducing bias. In this project, various data modeling methods were applied, such as **Robust Scaler**, **Min Max Scaler**, **Dummy Encoding**, **Label Encoding**, and **Nature Transformation**.


### **Step 6: Feature Selection**
In this step, I identified the attributes that are most relevant for explaining the phenomenon, and excluded any unimportant features that could introduce unnecessary noise during model training. The goal was to simplify the problem and improve model performance. To achieve this, I used the Boruta algorithm in combination with insights gained from EDA.

> 📘 Note
>
> The principle of parsimony, also known as Occam's Razor or the law of parsimony, states that when there are multiple possible explanations for a phenomenon or event, the simplest explanation is usually the correct one. In other words, the principle suggests that unnecessary assumptions or complexities should be avoided in scientific or philosophical explanations unless they are necessary to explain the observed data.
>
> This principle is often used as a guideline for constructing scientific theories and models, as it encourages researchers to favor explanations that are simple, elegant, and require the fewest assumptions or variables. By minimizing complexity and maximizing simplicity, the principle of parsimony aims to increase the clarity and accuracy of scientific explanations.

### **Step 7: Machine Learning Modeling**
In this step, I trained multiple machine learning models to determine the best fit for solving this particular problem.

### **Step 8: Hyper Parameter Fine Tuning**
In the Hyper Parameter Fine Tuning step, I selected the optimal values for the parameters of the model chosen in the previous step.

### **Step 9: Model Evaluation**
This is the step where I translated the performance of the machine learning model into a business result.

### **Step 10: Deployment**
In the final step, the project's end product is published in a cloud environment, allowing other individuals or services to access the results and utilize them to improve decision-making.


## 5. Top 3 Insights

> 📘 Note
>
> Insights can be generated in two ways:
> - **Surprise**: This occurs when the data reveals unexpected information to the business team, which may challenge their existing assumptions.
> - **Belief breach**: This happens when exploratory data analysis reveals something that contradicts the common sense or intuition of those involved. In such cases, the insights can help the team reassess their assumptions and make better-informed decisions.

### Insight 01
While the initial hypothesis suggests that stores with larger assortments will sell more, the analysis reveals that the opposite is true: **stores with greater assortments actually sell less**.

This revised version clarifies the contrast between the expected outcome (more sales with more products) and the actual outcome (less sales with more products).

![image](https://user-images.githubusercontent.com/100521949/233478003-a0b80c0d-c431-4b60-a413-7b1c52c1a244.png)

### Insight 02
Contrary to the initial hypothesis, the graphs show that **stores with closer competitors have a higher concentration of sales than those with competitors further away**.

![image](https://user-images.githubusercontent.com/100521949/233478164-60e64585-e80c-4093-a253-25ac474f6fe4.png)

### Insight 03
While it is commonly believed that stores that extend their promotional periods are more likely to increase their sales, the data actually suggest otherwise. In fact, the data shows that **extending promotions often leads to a decline in sales**.

![image](https://user-images.githubusercontent.com/100521949/233723264-85d339f0-42ba-4973-b27b-701d41e6f43a.png)

## 6. Machine Learning Models Applied
For this project, 5 models were considered: 
- **Average Model**
- **Linear Regression Model**
- **Linear Regression Regularized - Lasso**
- **Random Forest Regressor**, and 
- **XGBoost Regressor**

Initially, the Average Model was used as a baseline to evaluate the performance of other models. Two linear models were then tested to find out whether the problem could be approached linearly. Finally, two non-linear algorithms were evaluated, and the results of all five models are presented below.

## 7. Machine Learning Performance

### 7.1. Choosing the Algorithm
The Mean Percentage Error (MAPE) of the linear models was found to be greater than that of the Average Model. As a result, **it can be inferred that this is a nonlinear problem**.

#### Single performance
![image](https://user-images.githubusercontent.com/100521949/233423240-ebe7a310-7153-42b8-9712-1d43c6202d86.png)

#### Real performance - Cross Validation
![image](https://user-images.githubusercontent.com/100521949/233425050-d5e1570d-8179-4f25-9f12-4e4ff49a934e.png)

> 📘 Note
>
> Cross-validation is a common method in machine learning for evaluating the performance of a model on a dataset. It involves partitioning the dataset into several subsets, or "folds," and iteratively training and evaluating the model on different combinations of these folds.
>
> In k-fold cross-validation, the dataset is divided into k equally sized folds. The model is then trained on k-1 of these folds, and the remaining fold is used as the validation set to evaluate the model's performance. This process is repeated k times, with each fold being used once as the validation set.
>
> The advantage of cross-validation is that it allows for a more reliable estimate of the model's performance, since it uses all of the data for training and validation. This can help to avoid overfitting or underfitting the model to the dataset.

Once it was determined that the problem was nonlinear, the next step was to select the appropriate nonlinear algorithm to train for the project. Although the Random Forest Regressor exhibited better performance, **I ultimately decided to use the XGBoost Regressor for two reasons. First, as this was a study project, I wanted to gain a deeper understanding of the XGBoost algorithm, since more data was already available on the Random Forest Regressor. Additionally, as the project was deployed on a free cloud service with limited storage space, the smaller size of the XGBoost model made it a more practical choice.**

### 7.2. Evaluating the XGBoost Algorithm.

![image](https://user-images.githubusercontent.com/100521949/234361422-5547ccac-5753-4f05-b5df-756791e429c2.png)

- The first graph illustrates the day-by-day behavior of predictions over a period of six weeks. We can observe that the predicted values are very close to the actual sales values.

- In the second graph, if the value is equal to 1 I have a perfect prediction, for values above 1 the model is overestimating sales, which means that the sales values are higher than expected. While for values below 1 it is underestimating, that is, the predictions are smaller than the actual sales values.

- The third graph displays the error distribution, which is close to a normal distribution, indicating a well-fitted model.

- The last graph is a residual plot that depicts the relationship between predictions and errors. We can see that errors are larger for predictions between 7000 and 10000, but in general, they are below 10%.


## 8. Deployment

Once the solution has been validated, the CFO needs to be able to access the model for consultation. To achieve this, two APIs were developed: the Rossmann API, which receives user input regarding the store to be consulted and filters the corresponding data from the test dataset, and the Handler API, which utilizes the Data Preparation file to process the data and enable the trained model to make accurate predictions. The Handler API then returns the prediction to the Rossmann API, which delivers the result to the end user, as depicted in the diagram below.

![bot](https://user-images.githubusercontent.com/100521949/234112895-4848f33e-deb4-4b45-8c5c-055d0efd0494.png)

The Telegram Bot can be accessed through [this link](https://t.me/myRossmann_bot) and the video below shows how it works.

https://user-images.githubusercontent.com/100521949/234054958-b26f7501-ce30-4544-bd8f-a6176bdd69fa.mp4


## 9. Business Results



## 10. Conclusion
Overall, I believe that all the initial goals of the project were successfully achieved. The exploratory data analysis (EDA) provided valuable insights that can be leveraged to enhance the business (I listed some ideas in the Next Steps section below).The trained model performed exceptionally well for over 95% of the stores in the dataset, and the solution is easily accessible from a smartphone or computer device.

## 11. Next Steps

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
- Having a larger assortment does not necessarily result in increased sales. Therefore, a new project can be initiated to identify the top-selling products, and to reduce the stock of lower-performing products. This would lead to a reduction in stock costs while maintaining or potentially even increasing sales.
