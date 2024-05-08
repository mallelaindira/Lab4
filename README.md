# Lab4
Analyzing Student Performance
# Student Data Simulation and Linear Regression Model

The code provided is a simulation of student data and the subsequent building of a linear regression model to predict final grades based on various factors.

## Code Breakdown

Here's a breakdown of the code:

- The code begins by setting a fixed random seed using the `set.seed()` function. This ensures that the random numbers generated in the code are reproducible.
- The variable `num_students` is set to 500, representing the number of students for which the data will be simulated.
- The code then proceeds to simulate data for study hours, quiz scores, forum participation, previous grades, and final grades. Each variable is generated using the `sample()` function to randomly select values within specified ranges.
- A data frame named `student_data` is created to store the simulated data. It consists of columns representing study hours, quiz scores, forum posts, previous grades, and final grades.
- The `head()` function is used to display the first few rows of the generated data.
- The data is split into training and testing sets using an 80:20 ratio. The `sample()` function is again used to randomly select row indices for the training set, and the remaining rows are assigned to the testing set.
- A linear regression model is built using the training data. The formula `FinalGrades ~ StudyHours + QuizScores + ForumPosts + PreviousGrades` specifies that the final grades are the dependent variable, and the other variables are the independent variables. The `lm()` function is used to fit the model.
- Predictions are made on the test set using the trained model by calling the `predict()` function.
- Evaluation metrics, such as mean squared error (MSE) and R-squared, are computed to assess the model's performance. MSE measures the average squared difference between the predicted and actual values, while R-squared represents the proportion of the variance in the dependent variable that is predictable from the independent variables.
- The evaluation metrics are printed to the console using the `cat()` function.
- Prediction intervals are obtained by calling the `predict()` function with the `interval = "prediction"` argument.
- The lower and upper bounds of the prediction intervals are extracted from the `pred_int` object.
- The actual values from the test data are stored in the `actual_values` variable.
- The code checks if the actual values fall within the prediction intervals and computes the accuracy by counting the correct predictions.
- The accuracy is printed to the console using the `cat()` function.
- Finally, the trained linear regression model is displayed using the `model` object, and a plot of the model is generated using the `plot()` function.

## Usage

You can run this code to simulate student data and build a linear regression model for predicting final grades based on various factors. Make sure to have the necessary dependencies installed and follow the instructions in the code comments.

## License

This project is licensed under the [MIT License](LICENSE).
