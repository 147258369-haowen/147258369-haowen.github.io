# Random forest
## Decision tree
![](/images/desition_tree.png)

Decision tree is a very simple algorithm, which is highly explanatory and conforms to human intuitive thinking. This is a supervised learning algorithm based on if-then-else rules. The above picture can intuitively express the logic of the decision tree.

## Random forest
![](/images/random_forest.webp)
A random forest is composed of many decision trees, and there is no correlation between different decision trees.

When we perform a classification task, when a new input sample enters, each decision tree in the forest is judged and classified separately. Each decision tree will get its own classification result, which classification in the classification result of the decision tree At most, then Random Forest will take this result as the final result.

## Four steps to construct a random forest

1. Random sampling training decision tree
2. Randomly select attributes and make node split attributes
3. Repeat step 2 until it can no longer be split
4. Build a large number of decision trees to form a forest

# Pros and Cons of Random Forests
**advantage**

1. It can produce very high-dimensional (many features) data without dimensionality reduction or feature selection

2. It can judge the importance of features

3. Can judge the interaction between different features

4. Not easy to overfit

5. The training speed is relatively fast, and it is easy to make a parallel method

6. It is relatively simple to implement

7. For unbalanced data sets, it can balance the error.
Accuracy can still be maintained if a large fraction of features are missing.

**shortcoming**

1. Random forests have been shown to overfit on some noisy classification or regression problems.

2. For data with attributes with different values, attributes with more value divisions will have a greater impact on random forests, so the attribute weights produced by random forests on such data are not credible
