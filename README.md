# predict-brand-meaning
PROJECT FOR PREDICTING BRAND MEANING FROM EMPLOYEES' PERSPECTIVE

This research presents a supervised learning framework that applies machine learning models, including feedforward neural networks (FNNs), to predict brand perception and evaluate its drivers across employee and customer groups. The analysis focuses on two core constructs: brand meaning (“Do you know what your company’s brand means?”), and brand care (“Do you care about your company’s brand?”). Binary classification techniques are used for the two core constructs. The study identifies the most influential predictors associated with positive brand alignment by training models on structured organizational and behavioral data. It also evaluates how different metrics (e.g., precision, recall, F1-score, and AUC) capture performance across different Machine Learning (ML) models. The findings offer actionable insights into internal branding dynamics and demonstrate the practical value of machine learning in uncovering perceptual gaps and engagement drivers. The research is positioned at the intersection of applied AI, organizational analytics, and brand strategy.


I. MODELING BRAND PERCEPTION ACROSS EMPLOYEES

Understanding how a company’s brand is perceived internally is central to maintaining a consistent, impactful identity. In this study, we define and model two distinct yet interconnected brand constructs: brand meaning (whether employees/customers understand what the brand stands for) and brand care (the level of emotional and behavioral engagement with the brand). To streamline terminology, we refer to these constructs collectively as brand perception components.
My objective is to quantitatively model these components using supervised machine learning. Survey participants responded to direct binary questions such as "Do you know what your company’s brand means?" and "Do you care about your company’s brand?" These served as target variables for classification tasks.
Predictive feature sets were carefully chosen, preprocessed, and encoded to support multiple modeling pipelines, including FNNs and decision trees. For every research topic, the chosen feature set leads the interviewed employee to answer the corresponding “target” question. Based on all the answers to the target question, ML models predict the features’ importance and impact on the target question. 
By applying interpretable models alongside high-performing neural networks, I gain both predictive accuracy and actionable insights. Feature impact, as a key output metric, helps organizations understand not only what the brand perception is but why it exists—offering a foundation for strategic improvement.


II.	RESEARCH PROCESS AND DATA COLLECTION

For the purpose of this research, a Macedonian telecommunications operator was chosen, which offers to its customers a wide array of top excellence telecommunication services and contents within the scope of the fixed and mobile networks, broadband services, and integrated solutions, also including TV over Internet Protocol (IPTV). The company’s product portfolio includes Internet Protocol–based services, data transfer, sale and lease of equipment, and services for system integration.
A deductive research approach was used by using 2 different questionnaires:
•	Brand Meaning questionnaire, and
•	Brand Care questionnaire
The responses from these questionnaires are used to predict the impact of every metric on the corresponding target questions.
The datasets consisting these results were used as an input to two different tree-based ML models: Random Forest and CatBoost, as well as Feedforward Neural Network (FNN) with different architecture to predict the impact of every “feature” questions representing brand metrics on the “target” features Brand Meaning for the first, and Brand Care for the second questionnaire. I chose these two tree-based models because they are both powerful, non-linear models that can handle complex relationships between features and the target variable while being robust to overfitting and capable of handling categorical data efficiently. I also chose the FNN because it can capture complex, non-linear relationships between features and the target variable, leveraging its deep learning architecture to model intricate patterns in the data.
In order to determine the impact of each feature on the model‘s target prediction, I chose the SHAP (Shapley Additive exPlanations) method for both ML and FNN models.
Taking into account that the case company consists of four departments, from every different department 250 employees were interviewed, or in total 1.000 employees from the whole company. This representative sample was chosen regarding the company’s structure and its total number of employees.
The top impactful features from the 3 different models are shown in the corresponding tables. Every table consists of four columns: Feature (short description of the feature), Impact % (feature impact on the model‘s target prediction in percentage), Impact Direction (direction of the feature impact on the model’s target prediction – Inc. or Dec.), and Impact Strength (the strength of the feature impact on the model‘s target prediction – High, Medium or Low). For the purpose of this research, I chose only the most impactful features, both in positive and negative directions.
Comparing the features' impact of the three different models, it is clear that department features may capture hidden relationships or interactions with other features that the tree models cannot easily see.


A.	BRAND MEANING

The corresponding questionnaire consists of 12 questions which measure employee’s agreement on every metric in a Likert-scale from 1 to 5, and one “target” question - “Do the employees know what company’s brand mean?” which allows the employees to give a positive (yes) or negative (no) answer (“Table I”). The questions are considering different brand metrics: questions 1, 2, 3 and 4 (brand culture), questions 5 and 6 (brand personality), questions 7 and 8 (brand physique), questions 9 and 10 (brand relationship), question 11 (brand reflection) and question 12 (brand self-image). Further, questions 5, 6, 7, and 8 represent issues related to the company itself, whereas questions 11 and 12 reflect issues related to customers.
"Tables II, III, and V” show the impact of the features on the model‘s prediction regarding whether employees understand the meaning of their company’s brand for the three ML models: Random Forest, CatBoost, and FNN, and “Tables IV and VI” show the corresponding model test scores.
“Table II” shows that the increase in understanding the company mission and in knowing what to do to fulfill customer promises are the most positively impactful features on employees’ understanding of the brand meaning.
On the opposite end, decreasing the answers for customer needs fulfillment and for the influence of company’s mission, vision and values on employee’s work are the most negatively impactful features on employee’s understanding on the brand meaning.
From the “Table III”, it is clear that increasing the values about knowing what to do in order to fulfill customer promises and the influence of the mission, vision, and company values in employees’ everyday work are the most positively impactful features on their understanding of the brand meaning. On the opposite, decreasing the value of understanding the company vision has high negative impact on their understanding on the brand meaning.
Both ML models show high values for the evaluation metrics, as shown on “Table IV”.
For the FNN network, I used 16 input neurons (each input neuron for a different feature) and 1 output neuron for the “target”. To find the best-performing FNN architecture, I tested several architectures with 2 hidden layers with different numbers of neurons.
“Table V” shows that employee’s opinions from the services, marketing, and sales departments have a highly positive impact on the understanding of the brand meaning of all the company’s employees. On the opposite, employee’s opinions from the finance department have highly negative impact on the understanding of the brand meaning of all the company’s employees.
The best evaluation scores come from FNN (16, 48, 24, 1), shown in “Table VI”.


B.	BRAND CARE

The corresponding questionnaire consists of 10 questions which measure employee’s perception of importance on every metric in a Likert-scale from 1 to 5, and one “target” question – “Do employees care about their company’s brand?” which allows the employees to give a positive (yes) or negative (no) answer, as shown on “Table VII”.
Questions 1 and 2 reflect brand culture, questions 3 and 4 reflect brand personality, questions 5 and 6 reflect brand physique, questions 7 and 8 reflect brand relationship, question 9 reflects brand reflection, and, finally, question 10 reflects brand self-image.
"Tables VIII, IX, and XI” show the impact of the features on the model‘s prediction regarding whether employees understand the care of their company’s brand for the three ML models: Random Forest, CatBoost, and FNN, and “Tables X and XII” show the corresponding model’s test scores.
"Table VIII” shows that the increase in importance of the company’s offer of products and services, as well as the importance of the customers’ and company’s expectations, are the most positively impactful features on employees’ care about their company’s brand.
On the opposite end, the decrease in importance of applying and understanding a company’s mission, vision and values are the most negatively impactful features on employees’ care about their company’s brand.
“Table IX” shows that the impact is similar to that of the Random Forest model.
Both ML models show high values for the evaluation metrics, as shown on “Table X”.
For the FNN network, I used 13 input neurons (each input neuron for a different feature) and 1 output neuron for the “target”. In order to find the best-performing FNN architecture, I tested several architectures with 2 hidden layers with different numbers of neurons.
“Table XI” shows that employee’s opinions from the sales and services departments have highly positive impact on the employee’s care of their company’s brand. On the opposite, employee’s opinions from the finance and marketing departments have highly negative impact on the employee’s care about their company’s brand.
The best evaluation scores come from FNN (13, 39, 19, 1) as shown on “Table XII”.

IV.	CONCLUSIONS

In this study, three distinct ML models- Random Forest (RF), CatBoost, and Feedforward Neural Network (FNN)- were employed to analyze the impact of various features on brand perception. By comparing the identified top impact features from each model, I gain insights into the different ways each model approaches the feature importance problem.
The comparative analysis underscores the complementary nature of different ML models in understanding brand perception. While tree-based models highlight the importance of measurable, straightforward features, neural networks open the door to exploring deeper, less obvious aspects of brand perception. Future research could explore hybrid approaches, combining the strengths of both model types, to further refine the understanding of brand perception and its drivers.


