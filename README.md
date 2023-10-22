# Predicting Allergies Using Machine Learning

![Allergy Image](https://images.squarespace-cdn.com/content/v1/5e1f4478da9c6e2b148e8715/1613584583949-3JX5RW08AIJC5QUPVMUL/dr-lubitz-artificial-intelligence-healthcare-medicine-future-machine-learning-asthma-doctor-new-york-NYC-allergy)

## Introduction

Welcome to my project on predicting allergies using machine learning! In this GitHub README, I provide an overview of my research, data requirements, and objectives.

## Research Question

**Can Genetic Data and Historical Allergy Patterns Predict Susceptibility to Seasonal and Food Allergies?**

Allergies can significantly impact an individual's quality of life, and understanding one's susceptibility to allergies is crucial for personalized healthcare.

## Project Overview

My project is a continuation of previous research,  the study titled "Transgenerational Development of Food Allergies and Allergic Rhinitis." In this earlier work, I delved into the transgenerational aspects of allergy development. Now, I am taking this knowledge a step further by incorporating modern machine learning techniques to create an application that helps users understand their allergy susceptibility based on their unique genetic makeup and historical allergy patterns.

## Abstract from Previous Paper (Summarized)

Environmental and genetic factors both influence allergies, impacting immune cell function. Studies have explored the connection betIen parental allergies and allergic diseases in children. Specific toxins and health conditions, such as CO2, are associated with allergic rhinitis. Heritability from parents is a significant risk factor for allergies, particularly allergic rhinitis, which is more prevalent in males. Avoidance of certain foods increases the risk of developing allergies to those foods. T cells, CD4+ T cells, and common food allergens play key roles in allergic responses. Various therapies, such as Epicutaneous Immunotherapy (EPIT) and infant milk protein formulas, mitigate allergic reactions. Pollution and environmental factors, including sulfur dioxide, contribute to allergies. Therapies include early food introduction and specific formulas. More research on the genetic basis of allergies is needed for a comprehensive understanding.

## Conclusion from Previous Paper (Summarized)

In conclusion, allergic rhinitis (AR) is more common in males, and there's a strong link betIen parental AR and children. Exposure to toxins can lead to AR development or worsen its intensity. Understanding the genetic basis of allergies, including the roles of T cells and CD4+ T cells, is essential. Early peanut introduction reduces peanut allergies in children. Polymorphisms influence IgE levels and antibody production. Pollution, including sulfur dioxide, contributes to AR risk. Therapies like EPIT, early food introduction, and specific formulas offer effective strategies. Prevention, including childhood exposure and genetic research, can significantly advance my knowledge of allergies.

## Data Requirements

To address this research question effectively, there is a need of two main types of data:

### User Data

- Age
- Gender
- Location (city or region)
- Family history
- Previous allergies (seasonal, food, etc.)
- Allergies in childhood
- Dietary preferences (e.g., vegetarian, vegan)
- Smoking status (if applicable)
- Alcohol consumption (if applicable)
- Exercise habits
- Known exposure to common allergens (e.g., pets, pollen, dust mites)
- Any allergy symptoms experienced in the past (e.g., sneezing, itching, hives)
- Current medications or treatments for allergies (if applicable)
- Known food allergies
- Option to connect with genetic testing services (e.g., 23andMe) for more personalized results.

### General Data Set

In addition to user-specific data, I'll leverage a comprehensive general data set containing attributes such as ID or Participant Code, age, gender, location, family history, allergy types, symptoms, treatment, genetic data, and environmental factors. This rich dataset will allow us to explore broader trends and patterns in allergy susceptibility.

## Data Preprocessing

To ensure the quality and reliability of my dataset, I will begin by cleaning and preprocessing the data. This critical step involves handling missing values, encoding categorical variables, and scaling numerical features, setting the foundation for robust analysis and modeling.



# new code below
# Import necessary libraries
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score, classification_report

# Load your dataset
data = pd.read_csv("import numpy as np # linear algebra import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv) ​ # Input data files are available in the read-only "../input/" directory # For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory ​ import os for dirname, _, filenames in os.walk('/kaggle/input'):     for filename in filenames:         print(os.path.join(dirname, filename))")  # Replace "import numpy as np # linear algebra import pandas as pd # data processing, CSV file I/O (e.g. pd.read_csv) ​ # Input data files are available in the read-only "../input/" directory # For example, running this (by clicking run or pressing Shift+Enter) will list all files under the input directory ​ import os for dirname, _, filenames in os.walk('/kaggle/input'):     for filename in filenames:         print(os.path.join(dirname, filename))" with your dataset

# Split the data into features and target variable
X = data.drop(columns=["allergic"])
y = data["allergic"]

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Initialize and train a random forest classifier
clf = RandomForestClassifier(n_estimators=100, random_state=42)
clf.fit(X_train, y_train)

# Make predictions on the test set
y_pred = clf.predict(X_test)

# Calculate and print accuracy and classification report
accuracy = accuracy_score(y_test, y_pred)
print(f"Accuracy: {accuracy}")
print(classification_report(y_test, y_pred))

# Save the trained model for future use
import joblib
joblib.dump(clf, "allergy_model.pkl")  # Save the model to a file


---

