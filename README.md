Medical Diagnosis System using Bayesian Networks and Deep Learning
1. Abstract
This project presents a comparative study of two distinct approaches for medical diagnosis: Bayesian Networks and Deep Learning. We developed a system capable of predicting diseases based on a set of observed symptoms. A synthetic medical dataset was generated, encompassing various symptoms and corresponding disease labels. Both models were trained and evaluated on this dataset, with performance assessed using accuracy, classification reports, and confusion matrices. The objective is to highlight the strengths and weaknesses of each methodology in the context of medical diagnosis, providing insights into their practical applicability and potential for integration.
2. Introduction
Accurate and timely medical diagnosis is paramount for effective patient care. Traditional diagnostic methods often rely on physician expertise, clinical tests, and heuristic rules. However, the complexity of human biology and the vast array of possible symptoms and diseases make automated systems highly desirable. This project explores the application of two powerful machine learning paradigms—probabilistic graphical models, specifically Bayesian Networks, and connectionist models, represented by Deep Learning (Neural Networks)—to build a robust medical diagnosis system. The aim is to create a system that can assist healthcare professionals by offering data-driven diagnostic predictions, thereby enhancing efficiency and potentially improving patient outcomes.
3. Related Work
Automated medical diagnosis has progressed using Bayesian Networks and Deep Learning. Bayesian Networks effectively handle uncertainty and model relationships between symptoms and diseases. Deep Learning models like CNNs, RNNs, and MLPs achieve high accuracy in medical data analysis. This project combines both approaches for comparison on a symptom-disease dataset.
4. Existing System
Current diagnosis systems are either rule-based or data-driven. Rule-based systems are hard to maintain, while machine learning models struggle with uncertainty and lack transparency. This project addresses these issues using Bayesian Networks for interpretability and Deep Learning for improved accuracy.
5. Proposed Method
Our proposed medical diagnosis system integrates two distinct yet complementary methodologies: Bayesian Networks and Deep Learning. Both models are trained on a synthetically generated dataset comprising 1000 samples, each with 8 binary symptoms and 6 possible disease labels.
5.1 Synthetic Data Generation
To simulate a medical scenario, a synthetic dataset was created. For each of the 1000 samples, 8 symptoms (fever, cough, fatigue, headache, sore_throat, nausea, rash, muscle_pain) were randomly assigned a binary value (0 for no, 1 for yes). Diseases (common_cold, flu, allergies, food_poisoning, measles, malaria) were then assigned based on predefined logical combinations of these symptoms, with a fallback to random assignment for cases that didn't fit specific rules. This ensured a diverse and controllable dataset for model training and evaluation.
5.2 Data Preprocessing
The raw synthetic data underwent standard preprocessing steps:
1.	Feature-Target Separation: Symptoms (X) were separated from the disease labels (y).
2.	Label Encoding: Disease labels were converted from categorical strings to numerical integers using LabelEncoder (e.g., 'allergies': 0, 'common_cold': 1, etc.).
3.	Train-Test Split: The dataset was partitioned into training (70%) and testing (30%) sets to ensure unbiased model evaluation.
5.3 Bayesian Network (BN) Model
•	Model Structure: A simple Bayesian Network structure was defined where each symptom is considered a direct parent of the 'disease' node. This assumes that each symptom directly influences the probability of having a particular disease.
•	Parameter Learning: Conditional Probability Tables (CPTs) for the network were estimated from the training data (df_train_bn) using the MaximumLikelihoodEstimator from pgmpy. This estimator is suitable for discrete variables and aims to find parameters that maximize the likelihood of the observed data.
•	Inference: For prediction, VariableElimination was used for probabilistic inference. Given a patient's symptoms (evidence), the model queries the probability distribution over the 'disease' variable. The disease with the highest probability is then chosen as the prediction.
5.4 Deep Learning (Neural Network) Model
•	Architecture: A Multi-Layer Perceptron (MLP) will be constructed using TensorFlow/Keras. The architecture will consist of an input layer corresponding to the number of symptoms, one or more hidden layers with activation functions (e.g., ReLU), and an output layer with a softmax activation function for multi-class classification (predicting the probability of each disease).
•	Training: The neural network will be trained on the preprocessed training data (X_train, y_train_one_hot) using an appropriate loss function (e.g., categorical cross-entropy) and an optimizer (e.g., Adam).
•	Prediction: The trained model will predict disease probabilities for the test set (X_test), and the disease with the highest probability will be selected as the final prediction.
6. Results and Discussion 
6.1 Bayesian Network Results
•	Accuracy: 80.67% 
•	Performance varies across diseases. 
•	High precision for measles (few false positives). 
•	Lower precision for allergies (more misclassification). 
•	Good recall for flu (detects most cases). 
•	Confusion matrix shows overlap between similar diseases. 
Discussion:
The Bayesian Network provides reliable results with good interpretability but shows variation in performance across classes.
6.2 Deep Learning Results
(To be updated after implementation)
Discussion:
Will compare Deep Learning with Bayesian Network in terms of accuracy, strengths, and limitations.
7. Conclusion 
This project compares Bayesian Networks and Deep Learning for medical diagnosis. Bayesian Networks offer interpretability, while Deep Learning is expected to provide higher accuracy. Both methods have advantages, and future work can improve performance using real-world datasets.
8. Output
•	Dataset sample 
•	Train/test summary 
•	Bayesian Network results (accuracy, report, confusion matrix) 
•	Deep Learning results (accuracy, report, confusion matrix, training curves) 
9. References 
•	pgmpy 
•	scikit-learn 
•	TensorFlow/Keras 
•	Matplotlib 
•	Seaborn 
 

