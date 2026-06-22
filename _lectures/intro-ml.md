---
title: Introduction to Machine Learning
nav_order: 3
parent: Lectures
---

## Learning Objectives

By the end of this lecture, you should be able to:

- Explain what Machine Learning is.
- Distinguish between supervised, unsupervised, reinforcement, semi-supervised, self-supervised, hybrid, and transfer learning.
- Understand the basic training workflow of supervised learning.
- Explain the difference between training a model and using a trained model for prediction.

---

# 1. What Is Machine Learning?

**Machine Learning**, or **ML**, is a subfield of Artificial Intelligence where systems improve their performance on a task by learning from data, experience, or interaction with an environment.

Instead of explicitly programming every rule, we give the system data and define a learning process.

A traditional program usually works like this:

```text
Rules + input data → output
````

A Machine Learning system usually works like this:

```text
Training data + learning algorithm → trained model
```

Then, once the model has been trained:

```text
New input → trained model → prediction
```

The important idea is that the system does not receive all decision rules manually. It learns useful patterns from examples.

---

# 2. Main Types of Machine Learning

There are several types of learning:

* Supervised learning
* Unsupervised learning
* Reinforcement learning
* Self-supervised learning
* Hybrid or mixed learning
* Transfer learning

Each type of learning is useful for a different kind of problem.

---

## 2.1 Supervised Learning

**Supervised learning** is used when we have training examples with known answers.

Each example contains:

* Input data
* A correct output, also called a **label**

For example, suppose we want to recognize handwritten digits.

A training example may look like this:

```text
Input: image of a handwritten digit
Label: 7
```

The model receives many examples like this:

```text
Image 1 → label 5
Image 2 → label 0
Image 3 → label 4
Image 4 → label 7
```

The goal is for the model to learn the relationship between the input and the label.

After training, we can give the model a new image it has not seen before:

```text
New image → trained model → predicted digit
```

If the model has learned useful patterns, it may correctly predict:

```text
7
```

---

### 2.1.1 Classification and Regression

Supervised learning problems are often divided into two major types:

| Type           | Output         | Example                                      |
| -------------- | -------------- | -------------------------------------------- |
| Classification | Category/class | Predict whether an email is spam or not spam |
| Regression     | Number         | Predict the price of a house                 |

If the output is a class, the problem is classification.

Examples:

```text
Image → cat / dog / bird
Email → spam / not spam
Transaction → fraudulent / normal
```

If the output is a number, the problem is regression.

Examples:

```text
House size → house price
Years of experience → salary
Temperature → electricity demand
```

This lecture later focuses on **linear regression**, which is a supervised learning method for predicting numerical values.

---

## 3. Unsupervised Learning

**Unsupervised learning** is used when we have data without labels.

In supervised learning, the training data tells the model the correct answer.

In unsupervised learning, the data does not come with explicit correct answers.

For example, suppose we have images of different animals, but no labels:

```text
Image 1
Image 2
Image 3
Image 4
...
```

The model is not told:

```text
This is a fish.
This is a dog.
This is a bird.
```

Instead, the model tries to discover structure in the data.

For example, it may group similar images together:

```text
Group 1: fish-like animals
Group 2: dog/cat-like animals
Group 3: bird-like animals
```

---

### 3.1 Common Uses of Unsupervised Learning

Unsupervised learning is commonly used for:

* Clustering
* Data exploration
* Customer segmentation
* Anomaly detection
* Dimensionality reduction
* Pattern discovery

Example:

A company may have customer data but no predefined customer categories.

An unsupervised learning algorithm can group customers based on behavior:

```text
Group 1: frequent buyers
Group 2: occasional buyers
Group 3: inactive users
Group 4: high-value customers
```

The model does not know the meaning of each group in advance. A human analyst usually interprets the groups afterward.

---

## 3.3 Supervised vs Unsupervised Learning

| Aspect     | Supervised Learning                    | Unsupervised Learning              |
| ---------- | -------------------------------------- | ---------------------------------- |
| Data       | Has labels                             | Does not have labels               |
| Goal       | Learn input-output relationship        | Discover structure or patterns     |
| Output     | Prediction/classification              | Groups, patterns, representations  |
| Example    | Predict house price                    | Group similar customers            |
| Evaluation | Compare predictions with known answers | Harder; often needs interpretation |

The key difference is whether the training examples include known answers.

---

## 4. Reinforcement Learning

**Reinforcement Learning**, or **RL**, is a type of learning where an agent learns by interacting with an environment.

The basic components are:

| Component   | Meaning                                                   |
| ----------- | --------------------------------------------------------- |
| Agent       | The learner or decision-maker                             |
| Environment | The world/context where the agent acts                    |
| Observation | Information the agent receives from the environment       |
| Action      | What the agent does                                       |
| Reward      | Feedback signal indicating how good or bad the action was |

The general loop is:

```text
Agent observes environment
Agent chooses action
Environment changes
Agent receives reward
Agent updates behavior
```

The goal is for the agent to learn actions that maximize reward over time.

---

### 4.1 Reinforcement Learning Example

A common example is a game.

The agent is the player.

The environment is the game world.

The actions are moves the player can make.

The reward may be:

```text
+1 for scoring points
-1 for losing health
+100 for winning
-100 for losing
```

The agent does not necessarily receive the correct answer at every step. Instead, it learns from consequences.

This is different from supervised learning.

In supervised learning, the model receives examples with correct labels.

In reinforcement learning, the agent learns through trial and error.

---

### 4.2 Reinforcement Learning in Robotics

Reinforcement learning is also useful in robotics.

A robot may need to learn how to:

* Walk
* Balance
* Pick up objects
* Move through an environment
* Control a robotic arm
* Avoid obstacles

For example:

```text
Observation: robot is leaning too far left
Action: adjust motor movement
Reward: positive if balance improves, negative if robot falls
```

Over time, the agent can learn better behavior.

---

## 5. Other Forms of Learning

### 5.1 Semi-Supervised Learning

**Semi-supervised learning** uses a small amount of labeled data and a larger amount of unlabeled data.

This is useful because labeled data is often expensive.

For example, in medical imaging:

* Thousands of images may be available.
* Only a small number may be labeled by doctors.

Semi-supervised learning tries to use both:

---

### 5.2 Self-Supervised Learning

**Self-supervised learning** is a learning approach where the system creates a training signal from the data itself.

Instead of requiring humans to manually label every example, the model learns by solving automatically generated tasks.

Example in language:

```text
Input: The cat sat on the ___.
Target: mat
```

The model learns by predicting missing parts of the data.

Self-supervised learning is important in modern AI because many large models are trained using massive amounts of unlabeled text, images, audio, or video.

---

### 5.3 Hybrid or Mixed Learning

**Hybrid learning** combines different learning approaches.

For example, a system may combine:

* Supervised learning
* Unsupervised learning
* Reinforcement learning
* Human feedback
* Rule-based reasoning

This is common in real AI systems because one learning method is often not enough.

Example:

An autonomous vehicle may use:

* Supervised learning for object detection
* Reinforcement learning or planning for decision-making
* Rule-based safety constraints
* Sensor fusion for perception

---

### 5.4 Transfer Learning

**Transfer learning** means using knowledge learned from one task to help solve another task.

Instead of training a model completely from zero, we start with a model that has already learned useful patterns.

Example:

A neural network trained on millions of general images may already know how to detect edges, textures, shapes, and objects.

We can adapt it to a more specific task, such as:

```text
Classifying plant diseases
Detecting tumors in medical images
Recognizing industrial defects
```

Transfer learning is useful when we have limited data for the target task.
