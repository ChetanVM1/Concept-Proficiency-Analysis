# Concept-Proficiency-Analysis
## Concept Difficulty categorization Using Hierarchical Clustering

### Project Overview

Educational institutions often struggle to accurately assess the difficulty level of curriculum concepts and align learning content with student proficiency. This project aims to build an educational analytics framework that automatically classifies curriculum concepts into three difficulty levels—Easy (L1), Medium (L2), and Hard (L3)—using student assessment performance data.

The solution leverages Hierarchical Clustering to analyze concept-level learning patterns and generate data-driven difficulty classifications that can support adaptive learning systems and personalized education pathways.

Disclaimer: This demonstration uses simulated data solely to illustrate the modelling approach and analytical methodology. No actual or confidential organisational data has been used.

---

### Business Problem

In traditional learning environments, concept difficulty is often determined manually by subject matter experts. However, a concept perceived as easy by educators may actually be difficult for students based on assessment performance.

The objective of this project is to:

* Identify the actual difficulty level of curriculum concepts using student performance data.
* Understand how concept difficulty evolves over time.
* Support adaptive learning interventions by dynamically assigning difficulty levels.
* Improve student outcomes through personalized learning recommendations.

---

### Dataset Design

A synthetic educational dataset was created to simulate a real-world EdTech learning platform.

### Curriculum Coverage

* Grades: 4 to 10
* Subjects: Mathematics and Science
* Chapters per Subject: 12
* Concepts per Chapter: 5

Total Concepts:

840 Curriculum Concepts

### Assessment Structure

Students were evaluated through monthly assessments conducted over an 8-month academic period.

Assessment coverage expanded progressively:

| Month   | Chapters Covered |
| ------- | ---------------- |
| Month 1 | Chapters 1–4     |
| Month 2 | Chapters 1–5     |
| Month 3 | Chapters 1–6     |
| Month 4 | Chapters 1–7     |
| Month 5 | Chapters 1–8     |
| Month 6 | Chapters 1–9     |
| Month 7 | Chapters 1–10    |
| Month 8 | Chapters 1–12    |

---

### Features Used

For each concept in every monthly assessment, the following performance metrics were collected:

| Feature                | Description                                     |
| ---------------------- | ----------------------------------------------- |
| Correct Percentage     | Percentage of students answering correctly      |
| Incorrect Percentage   | Percentage of students answering incorrectly    |
| Unattempted Percentage | Percentage of students skipping questions       |
| Average Time (Seconds) | Average solving time spent on concept questions |

Additional engineered features included:

* Accuracy Ratio
* Engagement Ratio
* Speed Score


---

### Methodology

#### Data Preprocessing

* Missing values were validated and handled.
* Numerical features were standardized using StandardScaler.
* Feature distributions were analyzed to ensure consistency across grades and subjects.

#### Hierarchical Clustering

The project uses Agglomerative Hierarchical Clustering with Ward Linkage.

Ward linkage was selected because it:

* Minimizes within-cluster variance.
* Produces compact and interpretable clusters.
* Performs effectively on standardized educational performance metrics.

The clustering model groups concepts into three categories:

| Cluster   | Difficulty Level |
| --------- | ---------------- |
| Cluster 1 | Easy (L1)        |
| Cluster 2 | Medium (L2)      |
| Cluster 3 | Hard (L3)        |

A dendrogram was generated to visualize cluster formation and validate the hierarchical structure of concept difficulty levels.
For the cases, where 2 clusters were having better performance over 3 cluster models, the proficiency levels were defined as follows:
Cluster 0 shows concepts with better students average performance.

Cluster 1 shows concepts with poor students average performance.

L1 : Easy : 80 % concepts from cluster 0 and 20 % concepts from cluster 1.
L2 : Moderate : 60 % concepts from cluster 0 and 40 % concepts from cluster 1.
L3 : Hard : 20 % concepts from cluster 0 and 80 % concepts from cluster 1.

---

#### Statistical Validation

To evaluate the importance of predictive features, statistical testing was performed.

#### ANOVA Analysis

Analysis of Variance (ANOVA) was used to determine whether student grade level significantly influences concept performance metrics.

#### Cluster Quality Evaluation

The clustering solution was evaluated using:

* Silhouette Score
* Cophenetic Correlation Coefficient
* Dendrogram Analysis

These metrics helped validate cluster cohesion and separation.

---

### Results

#### Difficulty Classification

The model successfully classified 840 curriculum concepts into:

* Easy Concepts (L1)
* Medium Concepts (L2)
* Hard Concepts (L3)

based entirely on student performance patterns rather than manually assigned labels.

#### Improvement in Cluster Quality

Through iterative feature engineering and model refinement, clustering quality improved significantly.

| Month   | Cophenetic Coefficient |
| ------- | ---------------------- |
| Month 1 | 0.45                   |
| Month 8 | 0.68                   |

This represents a substantial improvement in cluster stability and interpretability over the course of the project.

#### Adaptive Learning Impact

Using the generated difficulty classifications, adaptive learning interventions were simulated to personalize student learning paths.

Disclaimer: This is a prototype designed to showcase the approach to a learning analytics business problem. The data used to demonstrate this prototype is entirely randomly generated and does not represent actual industrial data.

Observed outcomes:

* 40% improvement in average assessment scores for L1 students.
* 24% improvement in average assessment scores for L2 students.
* 32% improvement in average assessment scores for L3 students.

These results demonstrate the potential of data-driven curriculum adaptation to improve student learning outcomes.

---

### Key Learnings

* Applied unsupervised machine learning to solve an educational analytics problem.
* Built an end-to-end workflow covering data generation, preprocessing, clustering, validation, and business impact analysis.
* Evaluated feature significance using statistical testing techniques.
* Demonstrated how machine learning can support adaptive learning systems and personalized education strategies.

---

## Future Enhancements

* Incorporate student-level assessment records.
* Develop concept recommendation engines.
* Integrate real-time adaptive learning pathways.
* Compare Hierarchical Clustering with other clustering approaches.
