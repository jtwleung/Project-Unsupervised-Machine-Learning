# machine_learning_project-unsupervised-learning

## Project Outcomes

Goal:
- Use unsupervised learning techniques to build a 3+ learning models on a wholesale data dataset, to form groupings about customers of a wholesale grocery products company, based on their total spend on a number of categories of products (e.g. Grocery, Milk, Detergent_Products, Fresh food, Frozen food, Deli).
- Utilize the project dataset and requirements to hone the following skills:
- The project involves four main parts: exploratory data analysis and pre-processing, KMeans clustering, hierarchical clustering, and PCA. 
    - Exploratory data analysis using Pandas and Python methods and functions such as utility methods available in Pandas dataframes
    - Data Preprocessing and feature engineering
    - Training machine learning models using 3 methodologies:
        - KMeans Clustering
        - Hierarchical Clustering (Agglomerative Clustering)
        - PCA
    - Create and examine Elbow Plots for KMeans, to determine number of clusters to build the final model upon
    - Visualize clusters resulting from KMeans and Hierarchival Clustering (including Dendrograms in the latter).
    - Compare performance of models (by way of looking at the KMeans Centroid visualization and the Agglomerative Clustering dendrogram) when using Scaled vs. Non-Scaled data (the raw data is already all at the same scale: monetary units)
    - Model Evaluation and Interpretation of Findings on Model "Performance" (clustering)

### Duration:
- Project is intended to take:  Approximately 1 hour and 40 minutes
- Project took closer to 6-7 hours to complete, including applying KMeans, Agglomerative, and PCA tutorial approaches and lecture material to this novel dataset

### Project Description:
(Retained from the Original Lighthouse Labs Project Description)

In this project, we will apply unsupervised learning techniques to a real-world data set and use data visualization tools to communicate the insights gained from the analysis.

The data set for this project is the "Wholesale Data" dataset containing information about various products sold by a grocery store.
The project will involve the following tasks:

-	Exploratory data analysis and pre-processing: We will import and clean the data sets, analyze and visualize the relationships between the different variables, handle missing values and outliers, and perform feature engineering as needed.
-	Unsupervised learning: We will use the Wholesale Data dataset to perform k-means clustering, hierarchical clustering, and principal component analysis (PCA) to identify patterns and group similar data points together. We will determine the optimal number of clusters and communicate the insights gained through data visualization.

The ultimate goal of the project is to gain insights from the data sets and communicate these insights to stakeholders using appropriate visualizations and metrics to make informed decisions based on the business questions asked."

### Conclusions:
The following conclusions are also available within the Python Notebook entitled "Unsupervised Learning - Project.ipynb" and are copied here for ease of the reader:

1. KMeans clustering demonstrated that there appear to be 3 types or groupings of customers based on their total spend on various of 6 types of product categories.

2. Hierarhical clustering and the dendrogram also demonstrated there appear to be 3 types or groupings of customers based on their total spend on various of 6 types of product categories.

3. PCA analysis showed that 86% of the variance of the original dataset could be represented by 2 principal components (PC1 and PC2) that came out of the PCA analysis, while another 7%, bringing us up to 93%, of the variance of the original dataset can be represented by using 3 Principal Components (PC1, PC2 and PC3) of the dataset.  Given that there is a trade-off between keeping more dimensions or features to capture more of the original dataset's variance, vs. reducing dimensions to simplify downstream activities like visualizations and further model building, it is probably preferable to save only 2 Principal Components to represent this dataset which started at originally 6 dimensions.

4.  The 6 features (product categories) were of the same scale (they are "monetary units", according to the Kaggle site) so theoretically did not need to be scaled.  I scaled them for use in Kmeans and Agglomerative Clustering (Hierarchical) models in order to increase speed of convergence and because they are both distance-based.  However, the comparisons of the respective Centroid plots and Dendrograms showed that we got a cleaner and more "obvious" and tidy result when we did not scale.
    - It was also very difficult to interpret the Elbow Graph to decide on n_clusters with the scaled data since the resultant inertia values were also so small so as to be hard to see sharp elbows.  Trying n_clusters=5 that appeared like it *could* have been the optimal n_clusters for the scaled data showed that the clusters were not optimal and that we should have stuck with n_clusters=3, which is what the non-scaled Elbow Graph showed.
    - Perhaps a different type of scaling could have been attempted, which would still reduce the numbers for faster convergence, but not make them so "small" which would have made the inertia scores and distance-to-centroid calculations not as small, and the resultant graphs easier to read and models perhaps have greater utility.
    - This was an interesting finding that using scaled data via the StandardScaler kind of "obfuscated" the obvious findings and the non-scaled data was better.

### Next Steps

This exercise demonstrated to me the areas where I would like to gain more understanding and expertise in, including:
1. Investigate the different Scalers and see if there are ways to Scale the data (for easier convergence and efficiency for distance-based algorithms) without really shrinking it down to such small numbers which then makes the inertia scores that help generate the Elbow Graph harder to read, and seemed to somewhat distort the KMeans clustering (the Centroid plot for Scaled Data looked a bit more 'untidy' and 'not as obvious').

2. Learn how to investigate the tradeoff between predictive power and simplicity from:

    a) keeping 3 Principal Components (PC1, PC2 and PC3) which would capture 93% of the variance of the original dataset, versus
    
    b) keeping only 2 Principal Components (PC1 and PC2) which captures 86% of the variance of the original dataset, the increased complexity of keeping an extra dimension

    Questions to answer:
    
    - For downstream applications such as visualization and feeding into further models, does having 3 dimensions really cause more problem that gaining a 7% retention of variance is worth?
    - How can this tradeoff be quantified?

3. Learn if there are more out-of-the-box functions or methods for graphing and visualization the KMeans clusters generated, the Elbow Graph, and the Dendrogram, without having had to rely upon code written by Amir Parizi.