# Supervised Learning VS Unsupervised Learning
### Conclusion:
- **Supervised learning: the training dataset is labeled with the answer.**
- **Unsupervised Learning: The training dataset isn't labeled with the answer.**

### Supplement:
**Supervised Learning**:
- **Definition**: The training dataset includes labeled data, which means that each training example is paired with an output label. The model learns to map inputs to the correct output based on these labels.
- **Goal**: Predict the correct output labels for new, unseen data.
- **Common Algorithms**: Linear regression, logistic regression, support vector machines (SVM), decision trees, random forests, neural networks.
- **Examples**:
    - **Classification**: Email spam detection (spam or not spam), image recognition (cat, dog, or other).
    - **Regression**: Predicting house prices, forecasting stock prices.

**Unsupervised Learning**:
- **Definition**: The training dataset is not labeled. The model tries to identify patterns and structures in the data without explicit instructions on what to look for.
- **Goal**: Discover the underlying structure of the data, such as grouping similar items or reducing data dimensionality.
- **Common Algorithms**: K-means clustering, hierarchical clustering, principal component analysis (PCA), t-distributed stochastic neighbor embedding (t-SNE), autoencoders.
- **Examples**:
    - **Clustering**: Customer segmentation in marketing, grouping similar documents.
    - **Dimensionality Reduction**: Reducing the number of features in a dataset while preserving important information.



----
# Easy steps to follow for ML
1. Observe the data. Charts are a good tool for observing the data.
2. Do feature engineering. Feature engineering involves preparing data for machine learning models through processes such as data cleaning, encoding categorical variables into numerical formats, and standardizing numerical data.
3. Create model, see model description below for more info.

## Brief explanation of some models from sklearn:
### 1. Logistic Regression

LogisticRegression()
- Description: Logistic Regression is a linear model used for binary classification. It models the probability of the default class (usually denoted as 0 or 1) using a logistic function.
- Advantages: Simple to implement, efficient for linearly separable data, interpretable coefficients.
- Disadvantages: Assumes linear relationship between the features and the log odds of the target, may not perform well on complex, non-linear data.

### 2. Decision Tree Classifier

DecisionTreeClassifier(criterion='entropy', random_state=0)
- Description: Decision Trees are non-linear models that partition the feature space into regions based on decision rules. Each internal node represents a feature, each branch represents a decision rule, and each leaf node represents an outcome.
- Advantages: Easy to understand and interpret, handles both numerical and categorical data, no need for feature scaling.
- Disadvantages: Prone to overfitting, especially with complex trees, sensitive to small changes in data.

### 3. Random Forest Classifier

RandomForestClassifier(n_estimators=100, random_state=0)
- Description: Random Forest is an ensemble method that creates a collection of decision trees (a forest) and aggregates their predictions. It reduces overfitting by averaging the results.
- Advantages: **Handles overfitting better than individual decision trees, robust to noise, works well with high-dimensional data.**
- Disadvantages: Can be computationally intensive, less interpretable than individual decision trees.

For example,
**1. Training the Model:**
- Bootstrap Sampling: Randomly sample the training data with replacement to create multiple subsets (bootstraps).
- Growing Trees: For each subset, grow a decision tree:
    - Random Feature Selection: At each node, a random subset of features is selected to determine the best split.
    - Splitting Criteria: Use criteria like Gini impurity or entropy to split the nodes.
- Tree Construction: Continue splitting until a stopping criterion is met (e.g., maximum depth, minimum samples per leaf).
**2. Making Predictions:**
- Aggregating Results: For classification, each tree votes on the class, and the majority vote is taken as the final prediction.

### 4. Support Vector Classifier (SVC)

SVC(kernel='linear', random_state=0)
- Description: Support Vector Machines (SVM) are powerful models for classification tasks. The linear SVC tries to find the optimal hyperplane that separates the data into classes with maximum margin.
- Advantages: Effective in high-dimensional spaces, robust to overfitting in high-dimensional space.
- Disadvantages: Can be slow to train with large datasets, less effective with noisy data.

**There is also a polynomial SVC as well!!!**

### 5. Gradient Boosting Classifier

GradientBoostingClassifier(random_state=0)
- Description: Gradient Boosting is an ensemble method that builds trees sequentially, each tree trying to correct the errors of the previous one. It uses gradient descent to minimize the loss. To conclude, training multiple decision trees in a sequential manner where each subsequent tree tries to correct the errors of the previous trees.
- Advantages: High performance, can handle mixed data types, flexible and robust.
- Disadvantages: Prone to overfitting if not tuned properly, can be slow to train due to sequential nature.

### 6. K-Nearest Neighbors Classifier

KNeighborsClassifier(n_neighbors=5)
- Description: K-Nearest Neighbors (KNN) is a simple, instance-based learning algorithm that assigns the class of a data point based on the majority class of its k nearest neighbors.
- Advantages: Simple to implement, non-parametric (no assumptions about data distribution), effective with well-separated data.
- Disadvantages: Computationally expensive with large datasets, sensitive to irrelevant or redundant features, requires feature scaling.

*For more examples and graphs, go to `4fun/Titanic - Machine Learning from Disaster (Kaggle challenge)/titanic.ipynb`.*

---
