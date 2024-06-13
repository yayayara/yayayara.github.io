---
title: "Introduction into Feature-based machine learning"
date: 2024-06-12 13:10:00 +0100
categories: [Cyber Data Analytics]
tags: [machine learning]
math: true
comments: false
---
This blog post series on Cyber Data Analytics is a course offered at the University of Twente in the Master’s program for Computer Science, specializing in cybersecurity. The course, provides theoretical and practical background for applying data analytics in the field of cyber security. "Anomaly detection is one of the main topics in cyber security. Specific difficulties that the student will learn to handle are the huge amounts of data and the large number of false positives. Behavioral profiling applies to both people and software processes. Different techniques will be taught to construct profiles from software logs. While building such profiles, care should be taken to not infringe upon the privacy of individuals the data is collected from. Finally, attackers will modify their behavior in order to avoid being detected, a cyber data analytics engineer tries to make their models/profiles robust against such modifications." Key topics covered include:

* Apply machine learning to real data
* Understand and modify machine learning algorithms
* Learn models from time series
* Detect anomalies in multidimensional time-series
* Use distributed processing to speed up machine learning
* Learn models from data streams with limited memory
* Learn sequential models
* Use machine learning for fingerprinting and profiling
* Preserve the privacy of data owners while learning models
* Learn robust models that can detect evasive attackers

## Machine Learning - What is it Good For?

*Advantages*:

* Machine learning can solve problems with unclear separations between answers by learning fuzzy borders.
* It automates complex problem-solving, reducing human workload.

*Disadvantages*:

* It's often unclear why a decision is made.
* Requires very large labeled datasets.
* Performance depends heavily on data quality.

**Challenges in Cyber Security with Machine Learning**:

1. **Data Imbalance**:
   * Most data is not part of an attack.

2. **Dynamic Data**:
   * Continuous stream of data to analyze, often with internal relationships.

3. **Adversaries Actively Bypass Learned Methods**:
   * Manipulate data for evasion.
   * Insert odd patterns in good examples to make bad examples look good.
   * Poison data during learning.

### Types of Machine Learning

1. **Supervised Learning**:
   * Samples have known labels, it learns from samples.
   * **Classification**: Predict discrete labels (e.g., malware vs. benign).
   * **Regression**: Predict continuous values (e.g., network bandwidth).

2. **Unsupervised Learning**:
   * Samples do not have known labels, it clusters data without known labels.
   * **Clustering**: Group similar data points together.

3. **Reinforcement Learning**:
   * Learns through trial and error, useful when the result isn't immediately clear (e.g., game strategies).

### The Machine Learning Workflow

1. **Identify Security Problem**:
   * Determine if the problem needs a data-driven solution.

2. **Data Collection & Labeling**:
   * Collect relevant data (pcap files, binaries, security logs, text).
   * Label data manually, automatically, or use unlabeled data.

3. **System Design & Learning**:
   * Identify the problem type (supervised vs. unsupervised, regression vs. classification).
   * Choose or design a suitable ML algorithm.
   * Train the algorithm on the collected data.

4. **Performance Evaluation**:
   * Test the algorithm on a separate set of data.
   * Evaluate performance regarding the security problem and runtime.

5. **Deployment & Operation**:
   * Implement the security solution.

### Feature-based Machine Learning

* **Feature Space**:
  * Data is described numerically as features, forming a feature space.
  * ML classifiers learn boundaries to separate samples with different labels.

* **Distance Function**:
  * Measures similarity or difference between two points in the feature space.
  * Must satisfy:
    * Identity: d(x,x) = 0
    * Positivity: If x ≠ y, d(x,y) > 0
    * Symmetry: d(x,y) = d(y,x) (
    * Triangle Inequality: d(x,z) ≤ d(x,y) + d(y,z) (

* **Distance Metrics**:
  * **Euclidean Distance (L2)**:
  *   \( \sqrt{\sum |x_i^2 + y_i^2|} \)
  * **Manhattan Distance (L1)**: To go from point A to B in a straight line, follow the road:
  *   \( \sqrt{|x_i + y_i|} \).
