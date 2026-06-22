---
title: Introduction to Linear Regression
nav_order: 4
parent: Lectures
---

## Learning Objectives

By the end of this lecture, you should be able to:

* Explain what linear regression is used for.
* Understand the idea of a hypothesis function.
* Identify the parameters of a one-variable linear regression model.
* Compute prediction error for one training example.
* Understand the cost function used in linear regression.
* Explain why training means minimizing the cost function.
* Understand why gradient descent is needed as an iterative optimization method.

---

## 1. Introduction to Linear Regression

**Linear regression** is one of the simplest supervised learning algorithms.

It is used when we want to predict a **numerical value** from input data.

For example:

| Input                | Output                       |
| -------------------- | ---------------------------- |
| Size of an apartment | Predicted price              |
| Years of experience  | Predicted salary             |
| Temperature          | Predicted electricity demand |
| Advertising budget   | Predicted sales              |

In this lecture, we focus on **linear regression with one variable**.

That means the model uses one input feature, usually written as $x$, to predict one output value, usually written as $y$.

Example:

$$
x = \text{apartment size}
$$

$$
y = \text{apartment price}
$$

The goal is to learn a function that receives the apartment size and predicts its price.

---

## 2. Supervised Learning Context

Linear regression is a **supervised learning** method.

In supervised learning, the training data contains examples with known answers.

For linear regression, the training data looks like this:

| Apartment size $x$ | Real price $y$ |
| :----------------: | :------------: |
|        80          |     120000     |
|       100          |     150000     |
|       150          |     230000     |
|       200          |     300000     |

Each row is a **training example**.

The model sees examples of apartment sizes and their real prices. From these examples, it tries to learn the relationship between size and price.

After training, the model should be able to predict the price of a new apartment.

Example:

$$
x = 130
$$

The model should produce something like:

$$
\hat{y} = 195000
$$

The symbol $\hat{y}$ is often used to mean “predicted value.”

---

## 3. The Hypothesis Function

In linear regression, the model is represented by a **hypothesis function**.

For one-variable linear regression, the hypothesis function is:

$$
h_w(x) = w_0 + w_1x
$$

This function represents a straight line.

The model receives an input $x$ and produces a prediction $h_w(x)$.

In the apartment example:

$$
h_w(x) = \text{predicted price}
$$

where:

$$
x = \text{apartment size}
$$

So if the model is:

$$
h_w(x) = 50000 + 1000x
$$

and the apartment size is:

$$
x = 120
$$

then the prediction is:

$$
h_w(120) = 50000 + 1000(120)
$$

$$
h_w(120) = 170000
$$

So the model predicts a price of:

$$
170000
$$

---

## 4. Parameters of the Model

The values $w_0$ and $w_1$ are called the **parameters** of the model.

The hypothesis function is:

$$
h_w(x) = w_0 + w_1x
$$

The parameters are:

$$
w_0, w_1
$$

Each parameter controls part of the line.

### 4.1 Intercept: $w_0$

The parameter $w_0$ is the **intercept**.

It controls where the line crosses the vertical axis.

If:

$$
h_w(x) = 50 + 2x
$$

then:

$$
w_0 = 50
$$

When $x = 0$:

$$
h_w(0) = 50 + 2(0) = 50
$$

So $w_0$ is the prediction when the input is zero.

---

### 4.2 Slope: $w_1$

The parameter $w_1$ is the **slope**.

It controls how much the prediction changes when $x$ increases.

If:

$$
h_w(x) = 50 + 2x
$$

then:

$$
w_1 = 2
$$

This means that every time $x$ increases by 1, the prediction increases by 2.

In the apartment example, if $x$ is size in square meters, then $w_1$ tells us how much the predicted price increases when the apartment size increases by one square meter.

---

## 5. What Does Training Mean?

Training a linear regression model means finding good values for:

$$
w_0, w_1
$$

The structure of the model is already defined:

$$
h_w(x) = w_0 + w_1x
$$

But we do not yet know which values of $w_0$ and $w_1$ produce the best line.

Different parameter values produce different lines.

For example:

$$
h_w(x) = 10 + 2x
$$

$$
h_w(x) = 50 + 4x
$$

$$
h_w(x) = 100 - x
$$

Each one is a different possible model.

The learning algorithm must find the values of $w_0$ and $w_1$ that make the model fit the training data as well as possible.

In simple terms:

> Training means adjusting the parameters so that the model makes better predictions.

---

## 6. Prediction Error

To know whether a model is good or bad, we need to measure its error.

For one training example, the prediction error is the difference between the predicted value and the real value.

For the $i$-th training example:

$$
\text{error}^{(i)} = h_w(x^{(i)}) - y^{(i)}
$$

where:

| Symbol         | Meaning                                          |
| -------------- | ------------------------------------------------ |
| $x^{(i)}$      | Input value of the $i$-th training example       |
| $y^{(i)}$      | Real output value of the $i$-th training example |
| $h_w(x^{(i)})$ | Predicted output for the $i$-th training example |

Example:

Suppose the real price is:

$$
y^{(i)} = 200000
$$

and the model predicts:

$$
h_w(x^{(i)}) = 180000
$$

Then the error is:

$$
h_w(x^{(i)}) - y^{(i)} = 180000 - 200000
$$

$$
= -20000
$$

The model underpredicted the price by $20000$.

---

## 7. Squared Error

Linear regression commonly uses **squared error**.

For one training example, the squared error is:

$$
\left(h_w(x^{(i)}) - y^{(i)}\right)^2
$$

First, positive and negative errors do not cancel when we combine errors across the training set.

For example, suppose two predictions have errors:

$$
-10
$$

and:

$$
10
$$

If we add the raw errors, they cancel:

$$
-10 + 10 = 0
$$

This would incorrectly suggest that the total error is zero.

But if we square each error first:

$$
(-10)^2 + (10)^2 = 100 + 100 = 200
$$

Now both mistakes contribute positively to the total error.

Second, larger errors are punished more strongly.

Example:

| Real value | Prediction | Error | Squared error |
| ---------: | ---------: | ----: | ------------: |
|        100 |         90 |   -10 |           100 |
|        100 |        110 |    10 |           100 |
|        100 |        150 |    50 |          2500 |

The last prediction is much worse, so its squared error is much larger.

---

## 8. Cost Function

A **cost function** measures how bad the model is over the entire training set.

For one-variable linear regression, the cost function is:

$$
J(w_0, w_1) = \frac{1}{2m} \sum_{i=1}^{m} \left(h_w(x^{(i)}) - y^{(i)}\right)^2
$$

where:

| Symbol         | Meaning                                    |
| -------------- | ------------------------------------------ |
| $J(w_0, w_1)$  | Cost function                              |
| $m$            | Number of training examples                |
| $x^{(i)}$      | Input of the $i$-th training example       |
| $y^{(i)}$      | Real output of the $i$-th training example |
| $h_w(x^{(i)})$ | Prediction for the $i$-th training example |
| $w_0, w_1$     | Model parameters                           |

The cost function computes the average squared error across the training set.

> The factor $\frac{1}{2m}$ is used instead of just $\frac{1}{m}$ mainly because it simplifies derivative calculations later. The $2$ cancels out when differentiating the squared term.

---

## 9. Intuition Behind the Cost Function

The cost function tells us how well the line fits the data.

If the line is far from many training points, the cost is high.

If the line is close to most training points, the cost is low.

A training point has a real value:

$$
y^{(i)}
$$

The model gives a predicted value:

$$
h_w(x^{(i)})
$$

The vertical distance between the prediction and the real value is the error:

$$
h_w(x^{(i)}) - y^{(i)}
$$

The cost function adds these errors over all training examples after squaring them.

So the cost function answers this question:

> On average, how wrong is the model?

---

## 10. Training Objective

The objective of linear regression is to find the parameters that minimize the cost function.

The hypothesis is:

$$
h_w(x) = w_0 + w_1x
$$

The parameters are:

$$
w_0, w_1
$$

The cost function is:

$$
J(w_0, w_1) = \frac{1}{2m} \sum_{i=1}^{m} \left(h_w(x^{(i)}) - y^{(i)}\right)^2
$$

The objective is:

$$
\min_{w_0, w_1} J(w_0, w_1)
$$

In words:

> Find the values of $w_0$ and $w_1$ that make the cost function as small as possible.

This means we want the model with the smallest average prediction error.

---

## 11. Why We Need an Optimization Method

At this point, we know what we want:

$$
\min_{w_0, w_1} J(w_0, w_1)
$$

But we still need a method to find the best values of $w_0$ and $w_1$.

We need a procedure that can:

1. Start with initial values for $w_0$ and $w_1$.
2. Compute how bad the current model is.
3. Adjust $w_0$ and $w_1$.
4. Reduce the cost function.
5. Repeat until the model is good enough.

This is where **gradient descent** becomes useful.

---

## 12. Gradient Descent: Basic Idea

**Gradient descent** is an optimization algorithm used to minimize a function.

In linear regression, the function we want to minimize is the cost function:

$$
J(w_0, w_1)
$$

The goal is:

$$
\min_{w_0, w_1} J(w_0, w_1)
$$

In words:

> Find the values of $w_0$ and $w_1$ that make the prediction error as small as possible.

The idea of gradient descent is simple:

1. Start with initial values for $w_0$ and $w_1$.
2. Use $h_w(x)$ to make predictions.
3. Compute the cost $J(w_0, w_1)$.
4. Update $w_0$ and $w_1$ in the direction that reduces the cost.
5. Repeat until the cost stops decreasing significantly.

A useful analogy is walking downhill.

Imagine the cost function as a landscape:

* High areas represent high error.
* Low areas represent low error.
* The goal is to move toward the lowest possible point.

Gradient descent uses the slope of the cost function to decide how each parameter should change.

---

## 13. The Gradient Descent Update Rule

For one parameter, the update rule has this general form:

$$
w_j := w_j - \alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
$$

where:

|                    Symbol                   | Meaning                                                       |
| :-----------------------------------------: | :------------------------------------------------------------ |
|                    $w_j$                    | A parameter of the model                                      |
|                   $\alpha$                  | Learning rate                                                 |
| $\frac{\partial}{\partial w_j} J(w_0, w_1)$ | Partial derivative of the cost function with respect to $w_j$ |


> **Notation note:**
> In an update rule like:
>
> $$
> w_j := w_j - \alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
> $$
>
> the value on the **left side** is the **new updated value** of $w_j$.
>
> The values on the **right side** are the **old/current values** before the update.
>
> So this should be read as:
>
> $$
> w_j^{new} = w_j^{old} - \alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
> $$
>
> The symbol $:=$ means **assign** or **update**. It does not mean that both sides were already equal before the operation.

---

### 13.1 Learning Rate

The value $\alpha$ is called the **learning rate**.

It controls how large each update step is.

If $\alpha$ is too small, gradient descent may be very slow.

If $\alpha$ is too large, gradient descent may overshoot the minimum and fail to converge.

In simple terms:

| Learning rate | Possible result              |
| :-----------: | :--------------------------- |
|   Too small   | Training is slow             |
|   Good size   | Cost decreases steadily      |
|   Too large   | Training may become unstable |

The learning rate is not learned automatically in basic gradient descent. It is usually chosen before training, so it is a **hyperparameter**.

---

### 13.2 The Gradient

The gradient tells us the **direction in which the cost increases fastest**.

Since our goal is to reduce the cost, gradient descent moves in the **opposite direction** of the gradient.

The update rule is:

$$
w_j := w_j - \alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
$$

The important part is the minus sign:

$$
-\alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
$$

That minus sign means:

> Move against the direction where the cost increases.

A simple way to think about it:

- If changing $w_j$ upward would make the cost go up, gradient descent moves $w_j$ downward.
- If changing $w_j$ downward would make the cost go up, gradient descent moves $w_j$ upward.

So gradient descent does not guess randomly. It uses the slope of the cost function to decide which direction reduces the error.

In short:

> The gradient points uphill. Gradient descent walks downhill.

---

## 14. Gradient Descent for One-Variable Linear Regression

For one-variable linear regression, the hypothesis is:

$$
h_w(x) = w_0 + w_1x
$$

The cost function is:

$$
J(w_0, w_1) = \frac{1}{2m} \sum_{i=1}^{m} \left(h_w(x^{(i)}) - y^{(i)}\right)^2
$$

Since the model has two parameters, gradient descent must update both:

$$
w_0
$$

and:

$$
w_1
$$

The general gradient descent rule is:

$$
w_j := w_j - \alpha \frac{\partial}{\partial w_j} J(w_0, w_1)
$$

For this case:

$$
j = 0
$$

and:

$$
j = 1
$$

So we need one update for $w_0$ and one update for $w_1$.

---

## 15. Partial Derivatives for Linear Regression

To use gradient descent, we need the derivative of the cost function with respect to each parameter.

The cost function is:

$$
J(w_0, w_1) =
\frac{1}{2m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)^2
$$

The hypothesis is:

$$
h_w(x) = w_0 + w_1x
$$

So, for one training example:

$$
h_w(x^{(i)}) = w_0 + w_1x^{(i)}
$$

Replacing this inside the cost function:

$$
J(w_0, w_1) =
\frac{1}{2m}
\sum_{i=1}^{m}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)^2
$$

---

### Derivative with respect to $w_0$

Start from the cost function:

$$
\frac{\partial}{\partial w_0} J(w_0, w_1) =
\frac{\partial}{\partial w_0}
\left[
\frac{1}{2m}
\sum_{i=1}^{m}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)^2
\right]
$$

Move the constant outside:

$$
\frac{1}{2m}
\sum_{i=1}^{m}
\frac{\partial}{\partial w_0}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)^2
$$

Apply the chain rule:

$$
\frac{1}{2m}
\sum_{i=1}^{m}
2
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)
$$

Cancel the $2$:

$$
\frac{1}{m}
\sum_{i=1}^{m}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)
$$

Replace $w_0 + w_1x^{(i)}$ with $h_w(x^{(i)})$:

$$
\frac{\partial}{\partial w_0} J(w_0, w_1) = 

\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)
$$

---

### Derivative with respect to $w_1$

Start from the cost function:

$$
\frac{\partial}{\partial w_1} J(w_0, w_1) = 
\frac{\partial}{\partial w_1}
\left[
\frac{1}{2m}
\sum_{i=1}^{m}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)^2
\right]
$$

Move the constant outside:

$$
\frac{1}{2m}
\sum_{i=1}^{m}
\frac{\partial}{\partial w_1}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)^2
$$

Apply the chain rule:

$$
\frac{1}{2m}
\sum_{i=1}^{m}
2
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)
x^{(i)}
$$

Cancel the $2$:

$$
\frac{1}{m}
\sum_{i=1}^{m}
\left(w_0 + w_1x^{(i)} - y^{(i)}\right)
x^{(i)}
$$

Replace $w_0 + w_1x^{(i)}$ with $h_w(x^{(i)})$:

$$
\frac{\partial}{\partial w_1} J(w_0, w_1) = 
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)x^{(i)}
$$

---

The difference is that the derivative for $w_1$ includes $x^{(i)}$.

This happens because $w_1$ multiplies the input $x$ in the hypothesis:

$$
h_w(x) = w_0 + w_1x
$$

The parameter $w_0$ affects the prediction as a constant shift.

The parameter $w_1$ affects the prediction depending on the value of $x$.


---

## 16. Final Gradient Descent Algorithm

Replacing the derivatives in the update rule gives the full algorithm for one-variable linear regression.

Repeat until convergence:

$$
w_0 :=
w_0 -
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)
$$

$$
w_1 :=
w_1 - 
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)x^{(i)}
$$

These two updates are repeated until the cost function stops decreasing significantly.

In words:

1. Compute the prediction error for each training example.
2. Add the errors across the dataset.
3. Use those errors to adjust $w_0$ and $w_1$.
4. Repeat the process until the line fits the data well enough.

---

## 16.1 Important: Update Simultaneously

The parameters $w_0$ and $w_1$ must be updated **simultaneously**.

That means we should compute the new values using the old values first, and only then replace both parameters.

Correct idea:

$$
temp_0 =
w_0 -
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)
$$

$$
temp_1 =
w_1 -
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)x^{(i)}
$$

Then update:

$$
w_0 := temp_0
$$

$$
w_1 := temp_1
$$

This matters because if we update $w_0$ first and then use the new $w_0$ to compute $w_1$, the algorithm no longer follows the intended gradient descent step.

---

## 17. What Convergence Means

Gradient descent repeats until it **converges**.

Convergence means that the algorithm has reached a point where the cost function is no longer improving significantly.

In practice, this may mean:

* $J(w_0, w_1)$ becomes very small.
* $J(w_0, w_1)$ stops changing much between iterations.
* The parameters $w_0$ and $w_1$ stop changing significantly.
* A maximum number of iterations is reached.

For simple linear regression with a well-behaved cost function, gradient descent can move toward the global minimum if the learning rate is appropriate.

---

## 18. Full Training Process

The complete training process for one-variable linear regression is:

1. Choose initial values for $w_0$ and $w_1$.

2. Define the hypothesis:

   $$
   h_w(x) = w_0 + w_1x
   $$

3. Use the hypothesis to make predictions on the training examples.

4. Compute the cost:

   $$
   J(w_0, w_1) = \frac{1}{2m} \sum_{i=1}^{m} \left(h_w(x^{(i)}) - y^{(i)}\right)^2
   $$

5. Use gradient descent to update $w_0$ and $w_1$.

6. Repeat until convergence.

7. Use the trained model to make predictions on new examples.

After training, the final model is still:

$$
h_w(x) = w_0 + w_1x
$$

But now $w_0$ and $w_1$ should have values that make the model fit the training data better.

---

## 19. Practice Questions

### Question

Explain why this update must be done using the old values of $w_0$ and $w_1$ and why both values need to be updated in the same step?

$$
w_0 :=
w_0 -
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)
$$

$$
w_1 :=
w_1 -
\alpha
\frac{1}{m}
\sum_{i=1}^{m}
\left(h_w(x^{(i)}) - y^{(i)}\right)x^{(i)}
$$

---

## 20. Suggested Resources

> **Suggested video:** StatQuest — Gradient Descent
> Useful for understanding the intuition behind moving step by step toward lower error.

<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/sDv4f4s2SB8"
  title="StatQuest — Gradient Descent"
  frameborder="0"
  allowfullscreen>
</iframe>

> **Suggested video:** StatQuest — Linear Regression
> Useful for reviewing how a line is fitted to data.

<iframe
  width="560"
  height="315"
  src="https://www.youtube.com/embed/7ArmBVF2dCs"
  title="StatQuest — Linear Regression"
  frameborder="0"
  allowfullscreen>
</iframe>
