# Resume Category Predictor & Skill Recommender (NLP-based)

This project is an NLP-powered resume categorization system that classifies resumes into predefined job categories and recommends top relevant skills for that role. Built using Python and machine learning techniques, it serves as a foundational tool for automating candidate evaluation in HR tech and recruitment systems.

✅ Model Accuracy: 99.48%
🎯 Model Type: Logistic Regression with TF-IDF
📄 Input Formats Supported: .pdf, .txt, .doc, .docx

## Problem Statement
Recruiters often receive a high volume of resumes, making it time-consuming to categorize candidates and match them with suitable job profiles. This project automates that process by:

- Predicting the Job Category of a candidate based on their resume content.

- Recommending Key Skills that align with the predicted role.

## Project Workflow
1. Data Preprocessing
- Loaded dataset containing resume text and corresponding job categories.

- Cleaned the text using custom cleanResume() function:

- Removed URLs, symbols, hashtags, mentions, and non-ASCII characters.

- Applied whitespace normalization.

2. Label Encoding
- Encoded job categories into numerical values using LabelEncoder.

- Saved the encoder as label_encoder.pkl for consistent decoding in the app.

3. Feature Extraction
- Used TF-IDF Vectorizer (with 5000 max features and English stopwords) to convert resume text into numerical format.

4. Model Training
- Applied Logistic Regression (max_iter=1000) for multi-class classification.

- Split dataset using an 80/20 train-test ratio.

5. Evaluation
- Achieved 99.48% accuracy on test data.

- Evaluated with accuracy_score and classification_report.

6. Model Serialization
- Saved the following for deployment:

- clf.pkl → Trained Logistic Regression model

- tfidf.pkl → TF-IDF vectorizer

- label_encoder.pkl → Label Encoder

🌐 Web Application
A Streamlit-based web app allows users to paste their resumes. Right now the app.py doesn't support uploading files in different formats.

The app:

- Extracts and cleans text.

- Predicts the resume category.

- Displays top 5 recommended skills for the category using a hardcoded skill mapping dictionary.

### Skills Mapping
The skills_mapping dictionary maps each predicted category to a curated list of essential industry-relevant skills. These are displayed dynamically based on the model’s prediction.

## Key Features
- Supports multiple resume formats

- Automated category prediction

- Relevant skill recommendations

- Cleaned and normalized NLP pipeline

- Reusable ML artifacts (.pkl files)

## Future Enhancements
🧠 Integrate Named Entity Recognition (NER) for skill extraction from resumes.

📈 Expand dataset for broader job roles and industries.

☁️ Deploy on cloud (e.g., Heroku, AWS, or Streamlit Cloud).

📥 Include a downloadable report summarizing prediction.

