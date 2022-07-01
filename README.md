# Disease_Prediction_from_fMRI_and_AAL_Atlas
This contains the code for the methods for prediction of disease status (CFS vs GWI vs control) on fMRI data using machine learning and the AAL atlas. 

Gulf War Illness (GWI) and Chronic Fatigue Syndrome (CFS) are debilitating conditions characterized by chronic widespread pain, fatigue, and cognitive impairment that are worsened by mild to moderate exertion (post-exertional malaise or exertional exhaustion). Controversy persists as to the origin of both as patient symptoms are sometimes perceived to be psychosomatic. As such finding objective biomarkers of disease status is crucial to help identify the condition in those afflicted. Our group previously identified that fMRI might be a useful tool to find objective biomarkers of CFS and GWI based on multivariate brain activation patterns. For these three studies our group used a series of machine learning algorithms combined with fMRI to identify unique patterns found in patients with CFS and GWI. 

Data was preprocessed by mapping activated voxels from fMRI scan to the Automated Anatomical Labeling (AAL) atlas. 

These three studies employed a standard machine learning pipeline of feature extraction, feature reduction, model training, model validation, and cross-validation. Data was split into a training and testing sample where the testing was not involved at all in feature selection or model training and was solely used as a holdout sample. 


Each AAL region was considered a separate feature for input to the model. The total number of significant voxels for each AAL region composed the input. Feature reduction steps included Pearson's Correlation analysis, recursive feature elimination (RFE), and finally the machine learning algorithm. Two studies utilized a logistic regression, the third an ensembled model (Composed of K-Nearest Neighbor, Linear Support Vector Machine (SVM), Decision Tree, Random Forest, AdaBoost, Naïve Bayes, Quadratic Discriminant Analysis (QDA), Logistic Regression model, and Neural Net).

Each model was validated on a separate testing set and final results were cross-validated using 5-fold cross validation. 

Full study and final results for each can be found here: 


https://www.frontiersin.org/articles/10.3389/fncom.2020.00002/full

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7407325/

https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7287630/


Included code files:

**Data_Preprocessing_and_EDA:**
Transforms voxel data into AAL regions and then identifies correlated regions. 

**Identify_and_Plot_Regions_of_Functional_Connectivity:**
General visualization code using Nilearn to create a series of stacked 2D slices showing what the activated voxels regions (from an fMRI scan) look like on the brain. 

**Model_Training:**
Generates and trains a logistic regression model on the activated brain regions identified in the EDA step to see if they are predictive of a disease state. 

**Model_Validation:**
Validates the model trained in the step above.

**Plot_CFS_Brain_Regions_from_Model:**
Visualizes the regions of the brain identified on fMRI scan of activity that corresponds to Chronic Fatigue Syndrome (CFS). This code requires brain scans to run. 

**Plot_GWI_Brain_Regions_from_Model:**
Visualizes the regions of the brain identified on fMRI scan of activity that corresponds to Gulf War Illness (GWI). This code requires brain scans to run. 

**Plot_Resting_State_Network**:
Demonstrates what a restating state network (through activated AAL regions) looks like on a 2D stacked visualization of the brain.

**To cite this project or use any of the code please refer to the following three studies:**

Provenzano, D., Washington, S. D., & Baraniuk, J. N. (2020). A Machine Learning Approach to the Differentiation of Functional Magnetic Resonance Imaging Data of Chronic Fatigue Syndrome (CFS) From a Sedentary Control. In Frontiers in Computational Neuroscience (Vol. 14). Frontiers Media SA. https://doi.org/10.3389/fncom.2020.00002 

Provenzano, D., Washington, S. D., Rao, Y. J., Loew, M., & Baraniuk, J. N. (2020). Logistic Regression Algorithm Differentiates Gulf War Illness (GWI) Functional Magnetic Resonance Imaging (fMRI) Data from a Sedentary Control. Brain sciences, 10(5), 319. https://doi.org/10.3390/brainsci10050319

Provenzano, D., Washington, S. D., Rao, Y. J., Loew, M., & Baraniuk, J. (2020). Machine Learning Detects Pattern of Differences in Functional Magnetic Resonance Imaging (fMRI) Data between Chronic Fatigue Syndrome (CFS) and Gulf War Illness (GWI). Brain sciences, 10(7), 456. https://doi.org/10.3390/brainsci10070456
