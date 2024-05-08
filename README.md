# Lab4
Analyzing Student Performance
set.seed(42)  # Set a fixed random seed for reproducibility
num_students <- 500  # Define the number of students

# Generate simulated data for study hours, quiz scores, forum posts, previous grades, and final grades
StudyHours <- sample(1:20, num_students, replace = TRUE)
QuizScores <- sample(1:10, num_students, replace = TRUE)
ForumPosts <- sample(1:30, num_students, replace = TRUE)
PreviousGrades <- sample(50:100, num_students, replace = TRUE)
FinalGrades <- sample(50:100, num_students, replace = TRUE)

# Create a data frame to store the generated data
student_data <- data.frame(StudyHours, QuizScores, ForumPosts, PreviousGrades, FinalGrades)

# Display the first few rows of the generated data
head(student_data)

# Split the data into training and testing sets with an 80:20 ratio
train_indices <- sample(1:num_students, 0.8 * num_students)
testing_data <- student_data[-train_indices, ]
training_data <- student_data[train_indices, ]

# Build a linear regression model using the training data
model <- lm(FinalGrades ~ StudyHours + QuizScores + ForumPosts + PreviousGrades, data = training_data)

# Compute predictions on the test set
predictions <- predict(model, newdata = testing_data)

# Calculate evaluation metrics: Mean Squared Error (MSE) and R-squared
MSE <- mean((predictions - testing_data$FinalGrades)^2)
R_squared <- summary(model)$r.squared

# Obtain prediction intervals
