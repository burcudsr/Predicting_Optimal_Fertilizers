# 🌿 Predicting Optimal Fertilizers

Machine Learning Classification project designed to predict the optimal fertilizer for various crops based on environmental conditions and soil nutrient profiles. This project was developed as part of the **Kaggle Playground Series - Season 5, Episode 6**.

### 🚀 Live Demo
Test the model here: [Fertilizer Recommendation App](https://huggingface.co/spaces/bdaser/Fertilizer)

### 📌 Problem
Predict the most effective fertilizer name based on soil characteristics (moisture, type), atmospheric data (temperature, humidity), and crop requirements (Nitrogen, Potassium, Phosphorous levels).

### 📊 Dataset
* **Training Data**: 750,000 entries.
* **Test Data**: 250,000 entries.
* Includes features for temperature, humidity, moisture, soil type, crop type, and NPK values.

### ⚙️ Workflow
* **Data Preprocessing & Cleaning**: 
    * Feature engineering to derive meaningful indices:
        * **Nutrient Ratios**: Calculated NP, NK, and PK ratios as indicators for developmental needs.
        * **Micro-climate Indices**: Created indices for moisture and humidity interaction to evaluate fertilizer solubility.
        * **Fertilizer Signatures**: Developed binary indicators to capture specific formulations (e.g., Urea or DAP signatures).
    * **Categorical Encoding**: Implemented `get_dummies` with `drop_first=True` to transform nominal features like `Soil Type` and `Crop Type` for model compatibility.

### 🏆 Model Performance
The system evaluates performance using the **Mean Average Precision @ 3 (MAP@3)** metric. Among the evaluated classifiers, **GradientBoostingClassifier** demonstrated superior results in accuracy and F1-score.

| Model | Accuracy | F1 Score |
| :--- | :--- | :--- |
| **GradientBoostingClassifier** | **0.168913** | **0.166738** |
| RandomForestClassifier | 0.162320 | 0.156613 |
| MultinomialNB | 0.149887 | 0.143524 |
