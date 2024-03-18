# Links

https://machinelearningmastery.com/cross-entropy-for-machine-learning/#:~:text=Cross-entropy%20can%20be%20used%20as%20a%20loss%20function,same%20quantity%20when%20used%20as%20a%20loss%20function.

https://medium.com/@HeCanThink/understand-information-content-entropy-cross-entropy-%EF%B8%8F-829addbf7c2b


# Information Content

- Information content, also known as self-information or surprise, is a fundamental concept in information theory that quantifies the amount of surprise or unexpectedness associated with an event or outcome. 

- It represents the minimum number of bits needed to encode or communicate the occurrence of the event.

- Example: 
  - The key idea behind information content is that rare or improbable events convey more information than common or expected events. For example, if you toss a fair coin and it lands heads up, the information content of this event is lower compared to the information content of the coin landing on its edge (an extremely rare event).

- The formula for calculating the information content of an event “X” with probability “P(X)” is:
  - Information(X) = -log2(P(X))
  - The negative sign ensures that information content is a positive quantity since P(X) is between 0 and 1
  - The base-2 logarithm is used in the formula, which allows the result to be measured in bits. This means that the information content of an event is the number of bits needed to represent that event’s occurrence in a binary system.

**Key points to note about information content:**

1. Rare events have higher information content because their probability is low, requiring more bits to communicate them.

2. Common events have lower information content because they are expected and convey less surprise.

3. Information content is additive. If two events are independent, the information content of their joint occurrence is the sum of their individual information contents.

4. Information content provides a way to measure uncertainty or the level of surprise associated with a particular event.


# Entropy

- Entropy is a fundamental concept in information theory, thermodynamics, and probability theory. 

- In the context of information theory, entropy measures the average amount of uncertainty or surprise associated with a random variable or probability distribution. It provides a way to quantify the amount of information required to describe or represent a set of outcomes.

- In information theory, entropy is often denoted by “H” and is calculated using the probabilities of the various outcomes of a random variable. For a **discrete** random variable “X” with probability distribution “P(X)”, the entropy “H(X)” is given by the formula:

```
H(X) = -Σ [ P(x) * log2(P(x)) ]

Where:

- “Σ” represents the sum taken over all possible values of “X”.
- “P(x)” is the probability of the event “x” occurring.
- “log2” is the base-2 logarithm.
```

**Key points to understand about entropy:**

1. Measuring Uncertainty: Entropy quantifies the level of uncertainty or randomness associated with a probability distribution. High entropy implies high uncertainty, while low entropy implies low uncertainty.

2. Equally Likely Outcomes: The entropy is maximized when all possible outcomes are equally likely. This means that there is the most uncertainty when all options are as likely as each other.

3. Coding Efficiency: Entropy is related to the minimum average number of bits needed to encode the outcomes of a random variable. Efficient coding schemes allocate fewer bits to more probable outcomes and more bits to less probable outcomes.

4. Information Content: Entropy is related to the average amount of information content per outcome. It can be thought of as a measure of surprise: a low-entropy distribution has less surprising outcomes, while a high-entropy distribution has more surprising outcomes.

5. Unit of Measurement: Entropy is typically measured in bits (when using base-2 logarithms) or nats (when using natural logarithms). A bit of entropy represents the amount of information needed to make a binary choice between two equally likely alternatives.

6. Application in Machine Learning: In machine learning, entropy is often used to measure the impurity or disorder of a set of data points. It’s commonly used in decision tree algorithms to determine the best attribute for splitting data.


# Cross Entropy

- Cross-entropy is a concept used to compare two probability distributions and quantify the difference between them. 

- It is a fundamental concept in information theory and is widely applied in machine learning, particularly in tasks involving classification and probabilistic modeling.

- Using cross-entropy as a loss function is a common practice in machine learning, particularly in tasks involving classification. It’s a way to measure the difference between the predicted probability distribution and the true distribution (one-hot encoded labels).

In the context of comparing two probability distributions “P(X)” and “Q(X)”, where “P(X)” represents the true distribution (e.g., actual labels) and “Q(X)” represents the predicted or estimated distribution (e.g., model’s probabilities), the cross-entropy “H(P, Q)” is calculated using the formula:

```
H(P, Q) = -Σ [ P(x) * log2(Q(x)) ]

Where:

- “Σ” represents the sum taken over all possible values of “X”.
- “P(x)” is the probability of the event “x” occurring according to the true distribution.
- “Q(x)” is the probability of the event “x” occurring according to the predicted distribution.
- “log2” is the base-2 logarithm.
```

**Key points to understand about cross-entropy:**

1. Measuring Difference: Cross-entropy measures how well the predicted distribution (“Q(X)”) approximates the true distribution (“P(X)”). It quantifies the difference between the two distributions in terms of information content.

2. Minimization Objective: In machine learning, especially in tasks like classification, the goal is often to minimize the cross-entropy. This effectively aims to make the predicted distribution as close as possible to the true distribution.

3. Relationship with Entropy: Cross-entropy is related to the entropy of the true distribution (“P(X)”), but it accounts for the differences introduced by the predicted distribution (“Q(X)”). When the predicted distribution perfectly matches the true distribution, the cross-entropy becomes equal to the entropy of the true distribution.

4. Loss Function: In machine learning, the cross-entropy is commonly used as a loss function to optimize models during training. The cross-entropy loss penalizes larger discrepancies between predicted and true distributions, encouraging the model to make more accurate predictions.

5. Numerical Stability: In practice, when dealing with probabilities close to zero (which can lead to undefined logarithms), it’s common to use a small positive constant (epsilon) to ensure numerical stability in the calculation of cross-entropy.

6. Applications: Cross-entropy is used in various machine learning algorithms, including logistic regression, neural networks, and decision trees. It’s particularly useful in tasks like classification, where the goal is to predict the probability distribution over classes.

