"# Simple_ML" 
GAME ANALYSIS IPYNB
Questions the analysis meant to answer
Question:
Which of the variables in the video game dataset or a combination of them best predicts ‘global sales’ of video games and why? Provide quantitative justifications for your answers.
Answer:
Based on the feature engineering/analysis we have performed on the video game dataset, the best predictors of ‘global sales’ are the four regional sales variables: ‘NA_Sales’, ‘EU_Sales’, ‘JP_Sales’, and ‘Other_Sales’. These variables have consistently shown high feature importance and correlation coefficients across all three models we have used: Gradient Boosting Regressor, Random Forest Regressor, and Linear Regression.
The combination of these four variables has resulted in the lowest mean squared error (MSE) and highest coefficient of determination (R^2) values among all the models we have used. This indicates that these variables are highly predictive of the target variable "Global_Sales".
Other variables such as "Critic_Score", "User_Score", "Year_of_Release", and "Genre" have also shown some degree of correlation with the target variable and have contributed to the prediction accuracy, but not as significant as the regional sales variables. We can conclude that the regional sales variables, especially in combination, are the best predictors of "global sales" of video games in this dataset.
Question:
What effect will the number of critics and users as well as their review scores have on the sales of Video games in North America, EU and Japan?
Answer:
The number of critics and users as well as their review scores can have a significant effect on the sales of video games in North America, EU, and Japan. In general, the more positive the reviews from both critics and users, the higher the sales of a video game tend to be. This is because positive reviews can increase overall awareness and interest in the game, leading to more sales. Conversely, negative reviews can have the opposite effect and decrease sales.
However, the impact of reviews can vary depending on the region. For example, a game that receives high scores from critics and users in North America may not necessarily do as well in Japan, as cultural and linguistic differences can affect how a game is received in different markets. Additionally, the size and preferences of the gaming market in each region can also play a role in determining how much of an impact review has on sales.
The number of critics and users reviewing a game can also influence sales. Generally, a higher number of reviews can indicate a larger audience for the game, which can lead to higher sales. However, it's also possible that a game with fewer reviews but higher overall scores could perform better than a game with many reviews but lower scores. Overall, the effect of reviews and the number of reviewers on video game sales can be complex and dependent on a variety of factors.

Question:
What propelled the choice of your regressor for this task? Aptly discuss with quantitative reasons!
Answer:
In choosing the regressor for this task, several factors were considered, including the nature of the dataset, the number and types of features, and the target variable. The dataset consists of both categorical and numerical features, and the target variable is continuous. This suggests the use of a regression model. The target variable (global sales) is expected to be influenced by a combination of features, some of which may interact with one another. Hence, we need a model that can capture non-linear relationships and interactions between features.
Linear regression is a simple and interpretable model that assumes a linear relationship between the predictors and the target variable. It is generally appropriate for datasets with a small number of variables and a linear relationship between the variables and the target. However, in our case, we have several variables, some of which may have non-linear relationships with the target variable, and the linear model may not capture these relationships adequately.
Gradient Boosting Regression and Random Forest Regression, on the other hand, are more complex models that can capture non-linear relationships between the predictors and the target variable. These models are also less prone to overfitting and can handle a larger number of variables compared to linear regression. 

To determine the best model for this task, we trained all three models on the dataset and evaluated their performance using the mean squared error (MSE) and the coefficient of determination (R-squared). The results showed that Gradient Boosting Regression and Random Forest Regression outperformed Linear Regression, achieving lower MSE and higher R-squared values. Between the two, Gradient Boosting Regression had slightly better performance than Random Forest Regression. 
Based on these quantitative justifications, Gradient Boosting Regression was chosen as the best model for this task. 
Question:
Use all the relevant categorical variables in the Video Game Dataset as the target variable at each instance and determine which of the variables performed best in classifying the dataset. Explain your findings. 
Answer:
Fig 2 shows that the performance of each categorical variable varied across the different models. For the 'Platform' variable, the Random Forest and Gradient Boosting models achieved the highest accuracy and F1 score, with values of 0.668 and 0.659, and 0.678 and 0.673, respectively. The SVM model performed poorly with an accuracy of 0.210 and F1 score of 0.097.
For the 'Genre' variable, the Random Forest and Gradient Boosting models again outperformed the SVM model, with accuracies of 0.521 and 0.552, and F1 scores of 0.503 and 0.542, respectively. The SVM model had an accuracy of 0.222 and F1 score of 0.088.
Finally, for the 'Rating' variable, the Random Forest model achieved the highest accuracy and F1 score, with values of 0.634 and 0.626, respectively. The Gradient Boosting model also performed well with an accuracy of 0.629 and F1 score of 0.625, while the SVM model had the lowest accuracy and F1 score, with values of 0.432 and 0.393, respectively.
The Random Forest and Gradient Boosting models performed well across all categorical variables, while the SVM model struggled to accurately classify the data. These findings suggest that the 'Platform' and 'Rating' variables may be more informative in classifying the video game dataset compared to the 'Genre' variable. However, it is important to note that these results are based on a single evaluation metric, and other factors such as interpretability and computational efficiency may also be important considerations when selecting a classification model. Overall results suggest that the Platform and Rating variables are better predictors of video game sales than the Genre variable. The random forest and gradient boosting models generally performed better than the SVM model, although this may depend on the specific dataset and problem at hand.

Question:
How did you check whether your models did not overfit?
Answer:
To check if the models did not overfit, I looked at the training accuracy and testing accuracy scores. If the training accuracy score is significantly higher than the testing accuracy score, it is an indication that the model may have overfit the training data. However, if the training accuracy score is similar to the testing accuracy score, then it suggests that the model is generalizing well to unseen data and not overfitting. In the given results, the Random Forest model achieved perfect training accuracy for all three variables, but the testing accuracy and F1 scores were lower. This suggests that the model may have overfit the training data, especially for the variable "Genre." The SVM model had low accuracy scores for both training and testing, which suggests that it did not overfit but also did not perform well in generalizing to unseen data. The Gradient Boosting model achieved reasonably high accuracy scores for both training and testing, which suggests that it did not overfit and was able to generalize well to unseen data.

Question:
Can your classification models be deployed in practice based on their performances? Explain. 
Answer:
Based on the results provided, The SVM models for all three categories - Platform, Genre, and Rating - had low training and testing accuracies, as well as low F1 scores. This suggests that the model is not able to accurately classify the data and may not perform well in practice. The Random Forest models had perfect training accuracies but varying testing accuracies and F1 scores. This suggests that the model may be overfitting to the training data, which could result in poor performance when deployed in practice. The Gradient Boosting models had moderate to high training accuracies, and the testing accuracies and F1 scores were also moderately high. This suggests that the model may be able to accurately classify the data and could potentially perform well in practice. 
It is important to fine-tune and carefully evaluate the performance of a classification model before deploying it in practice. The decision to deploy a model should be based on a variety of factors, including its accuracy, robustness, and ease of use, among others.

Question:
In the video game dataset, use a relevant categorical variable and other relevant non-categorical variables to form groups at each instance. By employing internal and external evaluation metrics, determine which categorical variable best describes the groups formed.

Answer:
Based on the evaluation metrics, it appears that the "Rating" categorical variable best describes the groups formed in the video game dataset. The Silhouette score, Calinski-Harabasz score, and Davies-Bouldin index are all higher for the groups formed using the "Rating" variable compared to the other categorical variables ("Platform" and "Genre"). 

This suggests that the groups formed using the "Rating" variable are more compact, well-separated, and have better defined centers than the groups formed using the other variables.
Furthermore, the Fowlkes-Mallows score is also highest for the groups formed using the "Rating" variable, indicating that these groups have the highest similarity with the true (global) labels.
Therefore, we can conclude that the "Rating" variable is the best categorical variable for forming groups in the video game dataset, based on the evaluation metrics we have calculated.
