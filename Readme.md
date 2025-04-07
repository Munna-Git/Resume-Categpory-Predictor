# Resume Category Predictor & Skill Recommender (NLP-based)

This project is an NLP-powered resume categorization system that classifies resumes into predefined job categories and recommends top relevant skills for that role. Built using Python and machine learning techniques, it serves as a foundational tool for automating candidate evaluation in HR tech and recruitment systems.

**✅ Model Accuracy: 99.48%**

**🎯 Model Type: Logistic Regression with TF-IDF**

**📄 Input Formats Supported: .pdf, .txt, .doc, .docx**

## **Problem Statement**
Recruiters often receive a high volume of resumes, making it time-consuming to categorize candidates and match them with suitable job profiles. This project automates that process by:

- **Predicting the Job Category** of a candidate based on their resume content.

- **Recommending Key Skills** that align with the predicted role.

## **Project Workflow**
1. ### **Data Preprocessing**
- Loaded dataset containing resume text and corresponding job categories.

- Cleaned the text using custom *cleanResume()* function:

- Removed URLs, symbols, hashtags, mentions, and non-ASCII characters.

- Applied whitespace normalization.

2. ### **Label Encoding**
- Encoded job categories into numerical values using *LabelEncoder*.

- Saved the encoder as *label_encoder.pkl* for consistent decoding in the app.

3. ### **Feature Extraction**
- Used *TF-IDF Vectorizer* (with 5000 max features and English stopwords) to convert resume text into numerical format.

4. ### **Model Training**
- Applied **Logistic Regression** (max_iter=1000) for multi-class classification.

- Split dataset using an 80/20 train-test ratio.

5. ### **Evaluation**
- Achieved **99.48%** accuracy on test data.

- Evaluated with *accuracy_score* and *classification_report*.

6. ### **Model Serialization**
- Saved the following for deployment:

- *clf.pkl* -> Trained Logistic Regression model

- *tfidf.pkl* -> TF-IDF vectorizer

- *label_encoder.pkl* -> Label Encoder

## 🌐 **Web Application**
A Streamlit-based web app allows users to paste their resumes. Right now the app.py doesn't support uploading files in different formats.

The app:

- Extracts and cleans text.

- Predicts the resume category.

- Displays top 5 recommended skills for the category using a hardcoded skill mapping dictionary.

### **Skills Mapping**
The *skills_mapping* dictionary maps each predicted category to a curated list of essential industry-relevant skills. These are displayed dynamically based on the model’s prediction.

## Key Features
- Supports multiple resume formats

- Automated category prediction

- Relevant skill recommendations

- Cleaned and normalized NLP pipeline

- Reusable ML artifacts (.pkl files)

## ⚙️ Challenges Faced During Deployment
Ah, deployment — the stage where dreams meet documentation and reality bites. 😅
So there I was, having built this near-perfect ML model, proud of my 99.48% accuracy, and then came the big question:

**“How do I make this available to others?”**

Naturally, I asked the wisest sage of our time, Google. It gave me few options and i chose to proceed with Streamlit. Sounds simple enough, right?

I confidently ran my model in Jupyter Notebook. Worked well. But when it came to turning this into an actual web app, I was hit with terms like .pkl, requirements.txt, virtual environments, a whole new ecosystem I didn’t sign up for (or so I thought).

First, I made a requirements.txt file. But it was just... a text file. I stared at it thinking, **“How is a .txt file supposed to make anything run?”** 😂 I had written the required libraries in there, so I figured the .pkl files probably needed some writing too. So what did I do? I copied my code and **pasted it inside empty .pkl files** - yes, literally. Rookie move, I know.

Next up: deployment on Streamlit. I gave it a go... and boom - error. Something about the .pkl files. I turned to more tutorials, and surprise - now I had five tabs open and ten different versions of advice. Still confused.

Then I thought, maybe it’s not Streamlit’s fault. Let’s try **Netlify**. Switched to that, only to realize: **Netlify is for static sites** and my ML model needed backend logic to function. Dead end. Again.

By now, my code was turning into a mini jungle - more snippets piling up with every tutorial watched and resources referred.

Finally I decided to ask one of my lecturers, showed her the model, and she patiently walked me through the process. And behold - she got it working on Streamlit. At that moment, I was relieved and very convinced this could work after all. 😌

We had a great one-hour conversation about ML, deployment, and best practices, and here's what I finally understood:
1.	Create a virtual environment
python -m venv venv
2.	Activate the environment
.\venv\Scripts\activate
3.	Install requirements
pip install -r requirements.txt
➡️ This is when I finally understood what that .txt file was doing.
4.	Run the app
streamlit run app.py

But wait... did it run without errors? Of course not. 😂
Turns out, the .pkl files I had dragged and dropped from VS Code were empty. I’d been dead set on using VS Code without realizing I needed to export the actual trained model from Jupyter and save it as a pickle file - not just create a blank one like a Word doc.

So, back to Jupyter I went, properly saved my model, TF-IDF vectorizer, and encoder as .pkl files, repeated the venv setup, and finally...

✨ It worked!


## Future Enhancements
🧠 Integrate Named Entity Recognition (NER) for skill extraction from resumes.

📈 Expand dataset for broader job roles and industries.

☁️ Deploy on cloud (e.g., Heroku, AWS, or Streamlit Cloud).

📥 Include a downloadable report summarizing prediction.

📈 Update the app.py file to actually map the suggested skills to the skills in the resume and  more enhancements can be made.

Author: Munna

📞 Contact 🔗 [LinkedIn](http://linkedin.com/in/munna-a4ab07253)