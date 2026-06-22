---
title: Introduction to Artificial Intelligence
nav_order: 1
parent: Lectures
---

## Learning Objectives

By the end of this lecture, you should be able to:

- Explain what Artificial Intelligence is.
- Understand why AI is useful for solving difficult or poorly defined problems.
- Distinguish between AI, Machine Learning, Deep Learning, and Generative AI.
- Identify common application areas of modern AI.
- Recognize the main disciplines that contribute to AI.
- Understand the two broad purposes of AI: building useful intelligent systems and understanding human intelligence.

---

# 1. What Is Artificial Intelligence?

Artificial Intelligence, usually abbreviated as **AI**, is a field of Computer Science focused on creating hardware and software systems that show intelligent behavior.

A system is usually considered “intelligent” when it can perform tasks that require abilities such as:

- Perception
- Reasoning
- Learning
- Decision-making
- Problem solving
- Adaptation
- Communication
- Planning

In simple terms:

> **Artificial Intelligence studies how to build machines that can perform tasks that normally require human intelligence.**

This does not mean that every AI system “thinks” like a human. Many AI systems solve problems using methods that are very different from human reasoning. What matters is that the system can produce behavior that appears intelligent in a specific task.

For example, an AI system may:

- Recognize objects in an image.
- Translate text from one language to another.
- Recommend movies or songs.
- Detect fraudulent transactions.
- Drive a car in certain environments.
- Play a game better than most humans.
- Answer questions using natural language.

---

# 2. Why Do We Need AI?

AI is especially useful when traditional programming is not enough.

In traditional programming, a developer writes explicit rules:

```text
If condition A happens, do action B.
If condition C happens, do action D.
````

This works well when the problem is clear, structured, and predictable.

However, many real-world problems are not like that.

For example, how would we manually write rules for recognizing whether an image contains a cat?

We could try rules like:

```text
If the image has pointy ears, whiskers, and fur, then it is probably a cat.
```

But this quickly becomes difficult.

What if:

* The cat is partially hidden?
* The image is blurry?
* The cat is a different color?
* The image contains a dog with similar features?
* The lighting is bad?
* The image contains multiple animals?

For this kind of problem, manually writing all rules is almost impossible. AI gives us tools to approach these problems differently.

Instead of programming every rule by hand, we can build systems that learn patterns from data.

---

# 3. Difficult Problems in AI

This course focuses on techniques for solving difficult or complex problems.

These difficult problems can be divided into two broad types:

## 3.1 Computationally Difficult Problems

Some problems are difficult for both humans and machines because they require searching through a very large number of possible solutions.

Examples include:

* Optimization problems
* Combinatorial problems
* Multi-objective problems
* Scheduling problems
* Route planning problems
* Resource allocation problems

A simple example is the traveling salesperson problem:

> Given a list of cities, find the shortest possible route that visits each city once and returns to the starting point.

This problem sounds simple, but the number of possible routes grows extremely fast as the number of cities increases.

For small cases, we can solve the problem directly. For large cases, brute force becomes impractical.

AI provides search, optimization, and approximation techniques to handle these situations.

---

## 3.2 Problems That Are Easy for Humans but Hard for Machines

Some tasks are easy for humans but difficult for machines.

Examples include:

* Recognizing handwritten characters
* Understanding speech
* Recognizing faces
* Understanding images
* Interpreting natural language
* Detecting patterns in noisy data
* Making decisions with incomplete information

A human child can often recognize a dog in a picture without knowing formal rules about geometry, color, texture, or anatomy.

For a computer, this is not simple.

The machine receives raw data: pixels, numbers, or signals. It must somehow transform that data into meaning.

This is one of the reasons why Machine Learning and Deep Learning became so important in modern AI.

---

# 4. The Development of Modern AI

Modern AI has advanced because of three major factors:

## 4.1 Data

AI systems, especially Machine Learning systems, need data.

Data allows the system to detect patterns, estimate relationships, and improve performance.

Examples of data used in AI:

* Images
* Text
* Audio
* Video
* Sensor readings
* User behavior
* Transactions
* Medical records
* Scientific measurements

The more useful and representative the data is, the better the system can learn.

However, more data does not automatically mean better AI. The quality, structure, and relevance of the data matter.

Bad data can produce bad models.

---

## 4.2 Better Algorithms and Optimization Methods

AI has also improved because the methods to train, search, optimize have improved.

An **algorithm** is a procedure: a sequence of steps used to solve a problem or perform a computation.

A **model** is a representation of a system, pattern, process, or relationship that can be used to make predictions, decisions, or explanations.

> In Machine Learning, the model is usually learned from data. A training algorithm adjusts the model so that its outputs become more accurate for a given task.

For example:

- A neural network is a **model architecture**.
- Backpropagation is an **algorithm** used to compute how the model should change.
- Gradient descent is an **optimization algorithm** used to update the model’s parameters.
- A trained neural network is the final **model** used for prediction.

So, when we say that AI improved because of “better algorithms,” we are mostly referring to better methods for:

- Searching through possible solutions
- Optimizing model parameters
- Training models more efficiently
- Representing knowledge or patterns
- Planning actions
- Learning from data
- Scaling models to larger datasets and more complex tasks

This includes improvements in algorithms, model architectures, and training procedures. Strictly speaking, those are not all the same thing, but they work together in practical AI systems.

---

## 4.3 Computing Power

Modern AI requires significant computation.

Training a model may involve millions or billions of numerical operations.

AI has grown partly because hardware has become more powerful and more accessible.

Important hardware and infrastructure include:

* CPUs
* GPUs
* TPUs
* Cloud computing
* Distributed computing
* Specialized AI accelerators

Deep Learning, in particular, became practical because GPUs made it possible to train large neural networks much faster than before.

---

# 5. Current Application Areas of AI

AI is now used in many areas.

## 5.1 Autonomous Vehicles

Autonomous vehicles use AI to understand the environment and make driving decisions.

They may need to:

* Detect pedestrians
* Recognize traffic signs
* Track nearby vehicles
* Estimate distance
* Plan routes
* Avoid obstacles
* Make decisions in uncertain situations

This requires combining Computer Vision, sensor fusion, planning, control systems, and Machine Learning.

---

## 5.2 Natural Language Processing

Natural Language Processing, or **NLP**, focuses on helping machines understand and generate human language.

Applications include:

* Translation
* Text summarization
* Chatbots
* Question answering
* Sentiment analysis
* Document classification
* Search engines
* Fake news or misinformation detection

Modern NLP has changed significantly because of large language models, such as transformer-based models.

These systems can generate text, answer questions, write code, summarize documents, and assist users through conversation.

---

## 5.3 Entertainment and Recommendation Systems

AI is widely used in entertainment platforms.

Examples include:

* Movie recommendations
* Music recommendations
* Video game AI
* Personalized feeds
* Content ranking
* Dating app matching
* User behavior prediction

These systems often learn from user interactions.

For example, if a user watches certain types of videos, the system may recommend similar content.

The goal is usually to predict what the user is likely to engage with.

---

## 5.4 Computer Vision

Computer Vision is the area of AI focused on interpreting visual information.

Common tasks include:

* Image classification
* Object detection
* Image segmentation
* Face recognition
* Optical character recognition
* Medical image analysis
* Video understanding

There is an important difference between these tasks:

| Task                 | Description                                         |
| -------------------- | --------------------------------------------------- |
| Image classification | Predicts the main category of an image.             |
| Object detection     | Finds objects and draws bounding boxes around them. |
| Segmentation         | Assigns a class label to each pixel or region.      |

Example:

An image classification model may say:

```text
This image contains a dog.
```

An object detection model may say:

```text
There are two dogs, one person, and one bicycle in the image.
```

A segmentation model may identify the exact pixels belonging to each dog, the person, and the bicycle.

---

## 5.5 Virtual Assistants and Agents

AI is also used to build assistants and agents.

Examples include:

* Customer support bots
* Personal assistants
* Coding assistants
* Scheduling assistants
* Educational tutors
* Workflow automation agents

An AI assistant may answer questions.

An AI agent goes further: it may take actions, use tools, retrieve information, plan steps, and interact with external systems.

For example, an AI agent might:

1. Read an email.
2. Extract a deadline.
3. Add a reminder to a calendar.
4. Summarize the task.
5. Notify the user.

This makes agents an important topic in modern AI.

---

## 5.6 Fraud Detection

AI is useful for detecting fraud because fraud patterns are often complex and change over time.

Examples:

* Credit card fraud
* Insurance fraud
* Identity theft
* Fake accounts
* Financial anomalies
* Suspicious transactions
* Fake news or manipulated content

Fraud detection systems often look for unusual patterns.

For example:

```text
A user normally makes small purchases in one country.
Suddenly, the account makes multiple large purchases in another country.
```

This may be flagged as suspicious.

AI does not always decide by itself. In many cases, it helps humans prioritize cases for review.

---

# 6. AI, Machine Learning, Deep Learning, and Generative AI

The terms AI, ML, DL, and Generative AI are related, but they are not the same.

```text
Artificial Intelligence
└── Machine Learning
    └── Deep Learning
        └── Generative AI
```

This hierarchy is not perfect in every case, but it is useful for understanding the relationship between the fields.

---

## 6.1 Artificial Intelligence

**Artificial Intelligence** is the broadest term.

It includes any technique that allows machines to show intelligent behavior.

AI includes:

* Rule-based systems
* Search algorithms
* Planning systems
* Expert systems
* Machine Learning
* Deep Learning
* Natural Language Processing
* Computer Vision
* Robotics

Not all AI uses Machine Learning.

For example, a chess engine may use search algorithms and handcrafted evaluation functions. That is still AI, even if it does not learn from data.

---

## 6.2 Machine Learning

**Machine Learning**, or **ML**, is a subfield of AI focused on systems that learn from data.

Instead of manually programming every rule, we provide examples and let the model learn patterns.

A simple definition:

> Machine Learning is the study of algorithms that improve their performance on a task through experience.

The “experience” usually comes from data.

Examples:

* Predicting house prices from historical sales data.
* Classifying emails as spam or not spam.
* Predicting whether a customer will leave a service.
* Recognizing handwritten digits.
* Grouping similar users together.

---

## 6.3 Deep Learning

**Deep Learning**, or **DL**, is a subfield of Machine Learning based mainly on neural networks with many layers.

Deep Learning is especially powerful for complex data such as:

* Images
* Audio
* Text
* Video
* Large-scale structured data

Deep Learning models can automatically learn useful internal representations.

For example, in image recognition:

* Early layers may detect edges.
* Middle layers may detect textures or parts.
* Later layers may detect objects.

Deep Learning is one of the main reasons modern AI has advanced so quickly.

---

## 6.4 Generative AI

**Generative AI**, or **GAI**, refers to AI systems that can generate new content.

Examples of generated content include:

* Text
* Images
* Audio
* Video
* Code
* Music
* 3D assets

Large language models are a major example of Generative AI.

A generative model does not only classify or predict labels. It creates outputs that resemble the data it was trained on.

Examples:

| Input                                     | Possible Generative AI Output           |
| ----------------------------------------- | --------------------------------------- |
| “Explain neural networks simply.”         | A paragraph explaining neural networks. |
| “Generate an image of a robot in a lab.”  | A synthetic image.                      |
| “Write a Python function to sort a list.” | Source code.                            |
| “Summarize this article.”                 | A shorter version of the article.       |

Generative AI is powerful, but it also has risks:

* It can produce incorrect information.
* It can hallucinate facts.
* It can reproduce biases from training data.
* It can be misused to create fake content.
* It may generate plausible but unreliable answers.

Because of this, AI systems must be evaluated carefully.

---

# 7. Long-Term and Short-Term Goals of AI

AI has both long-term and short-term goals.

## 8.1 Long-Term Goals

A long-term goal of AI is to develop systems with intelligence comparable to, similar to, or greater than human intelligence.

This is sometimes associated with the idea of Artificial General Intelligence, or **AGI**.

An AGI system would not be limited to one narrow task. It would be able to reason, learn, adapt, and solve many different types of problems.

Current AI systems are powerful, but they are still limited.

A model may be excellent at generating text but weak at physical reasoning.

Another model may classify images well but fail at planning.

So, while AI has achieved impressive results in specific areas, general human-level intelligence remains an open challenge.

---

## 7.2 Short-Term Goals

The short-term goal of AI is more practical:

> Build systems that perform specific tasks at a level comparable to or better than humans.

This already happens in many domains.

Examples:

* AI systems can classify some medical images with high accuracy.
* Chess and Go systems can defeat world champions.
* Speech recognition systems can transcribe audio in many situations.
* Translation systems can produce useful translations.
* Recommendation systems can process user behavior at massive scale.

These systems are usually narrow.

They are very good at the task they were designed for, but they do not necessarily understand the world broadly.

---

# 8. Disciplines That Contribute to AI

AI is interdisciplinary.

It uses ideas from several fields.

## 8.1 Philosophy

Philosophy contributes questions about:

* What is intelligence?
* What is reasoning?
* What does it mean to know something?
* Can machines think?
* What is consciousness?
* What is ethical behavior?

AI does not only involve technical implementation. It also raises deep conceptual and ethical questions.

---

## 8.2 Mathematics

Mathematics provides the formal tools used in AI.

Important areas include:

* Linear algebra
* Calculus
* Probability
* Statistics
* Optimization
* Logic
* Graph theory
* Information theory

For example, neural networks rely heavily on linear algebra and calculus.

Machine Learning relies heavily on probability, statistics, and optimization.

---

## 8.3 Psychology

Psychology helps AI researchers understand human behavior, learning, memory, perception, and decision-making.

Some AI systems are inspired by how humans solve problems.

For example:

* Reinforcement learning is related to learning from rewards and punishments.
* Cognitive architectures try to model aspects of human reasoning.

---

## 8.4 Neuroscience

Neuroscience help us understand the brain and nervous system.

Neural networks were originally inspired by biological neurons, although modern artificial neural networks are much simpler than real brains.

---

## 8.5 Linguistics

Linguistics contributes to Natural Language Processing.

It helps with understanding:

* Syntax
* Semantics
* Pragmatics
* Morphology
* Phonetics
* Discourse
* Ambiguity in language

Modern NLP uses statistical and neural methods, but linguistic ideas are still useful for understanding language structure.

---

## 8.6 Computer Science and Engineering

Computer Science and Engineering provide the systems, algorithms, and infrastructure needed to build AI.

Relevant areas include:

* Algorithms
* Data structures
* Software engineering
* Databases
* Distributed systems
* Operating systems
* Computer architecture
* Robotics
* Cloud computing
* Security

AI is not only about models. Real AI systems require reliable software, scalable infrastructure, and careful engineering.

---

# 9. The Purpose of AI

AI has two broad purposes.

## 9.1 Using Computers to Extend Human Ability

The first purpose is practical:

> Use computational resources to amplify human thinking, productivity, and problem-solving.

This is similar to how engines amplify physical power.

Humans use machines to move faster, lift heavier objects, and produce more energy.

AI can similarly help humans:

* Analyze large amounts of data.
* Automate repetitive tasks.
* Detect patterns humans may miss.
* Make better decisions.
* Solve complex problems.
* Build more useful software.
* Improve education, medicine, transportation, and science.

Examples:

* Expert systems
* Robotics
* Machine Learning systems
* Decision-support tools
* AI assistants
* Search engines
* Medical diagnosis tools

In this view, AI is a tool for extending human capability.

---

## 9.2 Understanding Human Problem Solving

The second purpose is scientific:

> Use AI to better understand how humans solve problems.

This connects AI with cognitive science.

The goal is not only to build useful machines, but also to study intelligence itself.

Questions include:

* How do humans reason?
* How do humans learn?
* How do humans represent knowledge?
* How do humans make decisions?
* How do humans solve unfamiliar problems?
* How does perception work?
* How does language understanding work?

AI can be used as a way to test theories about intelligence.

If we create a computational model of reasoning, we can compare its behavior with human reasoning.

This does not mean the model is exactly like the human mind, but it can help researchers explore possible explanations.

---

# 10. AI as a Problem-Solving Discipline

A useful way to understand AI is this:

> AI is not only about making machines “smart.” It is about solving problems that are hard to solve using traditional programming.

This includes problems where:

* The search space is too large.
* The rules are unclear.
* The data is incomplete.
* The environment changes.
* The answer is uncertain.
* Human-like perception is needed.
* Learning from examples is better than writing rules manually.

AI combines theory, algorithms, data, and computation to build systems that can act intelligently in these situations.

---

# 11. Example: Traditional Programming vs Machine Learning

Suppose we want to build a spam email detector.

## Traditional Programming Approach

We might write rules like:

```text
If the email contains "free money", mark it as spam.
If the email contains many links, mark it as spam.
If the sender is unknown, increase spam score.
```

This may work for simple cases, but spammers can adapt.

They can change words, hide links, or imitate normal emails.

The rule system becomes hard to maintain.

## Machine Learning Approach

Instead, we collect many examples:

```text
Email 1 -> spam
Email 2 -> not spam
Email 3 -> spam
Email 4 -> not spam
```

Then we train a model to find patterns.

The model may learn that spam emails often have certain word patterns, formatting, sender behavior, or metadata.

The programmer does not manually write every rule. The model learns from examples.

This is one of the central ideas of Machine Learning.

---

# 12. Key Terms

| Term                        | Meaning                                                                     |
| --------------------------- | --------------------------------------------------------------------------- |
| Artificial Intelligence     | Field focused on creating systems with intelligent behavior.                |
| Machine Learning            | Subfield of AI where systems learn patterns from data.                      |
| Deep Learning               | Subfield of ML based on multi-layer neural networks.                        |
| Generative AI               | AI systems that generate new content such as text, images, audio, or code.  |
| Algorithm                   | Step-by-step procedure for solving a problem.                               |
| Model                       | A learned or designed representation used to make predictions or decisions. |
| Training                    | Process of adjusting a model using data.                                    |
| Data                        | Examples or observations used by AI systems.                                |
| Optimization                | Process of finding better or best solutions according to an objective.      |

---

# 13. Common Misconceptions

## Misconception: Deep Learning is always the best solution

Deep Learning is powerful, but it is not always necessary.

For some problems, simpler models are better because they are:

* Easier to train
* Easier to interpret
* Faster
* Cheaper
* More reliable with small datasets

---

## Misconception: More data always means better AI

More data can help, but only if the data is relevant and high quality.

Bad data can produce bad results.

Common data problems include:

* Missing values
* Wrong labels
* Bias
* Duplicates
* Outdated examples
* Unrepresentative samples

---

## Misconception: AI systems understand everything they generate

Generative AI can produce fluent text, but fluency is not the same as understanding.

A model may generate an answer that sounds correct but is factually wrong.

This is why verification and evaluation are important.
