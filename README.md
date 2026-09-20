# RASSAD — AI-Based Compliance Monitoring System for Data Privacy under the Saudi Personal Data Protection Law (PDPL)

RASSAD is an AI-based compliance monitoring system developed to support organizations in Saudi Arabia in identifying potential violations of the **Personal Data Protection Law (PDPL)** using Natural Language Processing (NLP), deep learning, and Explainable AI (XAI).

## About the Project

Manual PDPL compliance review can be time-consuming, particularly when analyzing large amounts of organizational and legal text.

RASSAD automates the process by detecting potential PDPL violations, explaining the model's predictions, and providing corrective recommendations for the identified violation type.

## System Components

### 1. Violation Classification

The classification module analyzes input text and classifies it into one of **17 PDPL violation categories** or **No Violation**.

### 2. Explainable AI (XAI)

The XAI module uses the **Integrated Gradients** technique through the Captum library to highlight the most influential words contributing to the model's prediction.

The explanation is presented with supporting evidence and the relevant PDPL requirement to help users understand the basis of the prediction.

### 3. Recommendation Module

A rule-based recommendation module provides practical corrective actions based on the identified violation type.

### 4. Interactive Dashboard

RASSAD is implemented as a bilingual **Arabic/English Streamlit application** with the following pages:

* Home
* Check Compliance
* PDPL Standards
* Dashboard
* History

The Check Compliance page allows users to enter text directly or upload **PDF, DOCX, or TXT** files for analysis.

## Datasets Used

Multiple datasets and sources were integrated and preprocessed during the development of the system, including:

* Synthetic PII Finance — Gretel.ai
* Nemotron-PII — NVIDIA
* PII External Dataset — Kaggle
* Synthetic Dataset for PII Detection in Financial Documents — Mendeley
* Official PDPL legal text
* World's Biggest Data Breaches and Hacks — Kaggle
* GDPR Violations and Sanctions — GitHub

## Models & Results

Four deep learning approaches were developed and evaluated for multi-class violation classification:

| Metric    | DistilRoBERTa |     BiLSTM |  XLNet | TextCNN |
| --------- | ------------: | ---------: | -----: | ------: |
| Accuracy  |        93.85% | **94.65%** | 91.17% |  84.20% |
| Macro F1  |    **89.99%** |     88.53% | 74.52% |  59.42% |
| Precision |        93.86% |     95.00% | 90.72% |  83.15% |
| Recall    |        93.85% |     94.65% | 91.17% |  83.15% |

**DistilRoBERTa** was selected as the final model based on its overall performance across the violation classes, particularly its Macro F1-score.

## Technology Stack

* Python
* PyTorch
* Hugging Face Transformers
* DistilRoBERTa
* Scikit-learn
* Captum
* Streamlit
* Natural Language Processing (NLP)

## Demo Screenshots

### Home Page

![Home Page](assets/screenshots/Home%20Page.png)
### Compliance Check — Violation Detection

![Check Page](assets/screenshots/Check%20Page.png)
The Check Compliance page allows users to enter text directly or upload a PDF, DOCX, or TXT document. The system analyzes the content and identifies potential PDPL violations and their violation type.

### Explainable AI & Recommendations

![XAI & Recommendations](assets/screenshots/Check%20XAI.png)
This view continues the compliance analysis by presenting the XAI explanation of the prediction along with corrective recommendations for the identified violation.

### PDPL Standards

![PDPL Standards](assets/screenshots/Standers%20Page.png)
A reference page presenting the articles and requirements of the Saudi Personal Data Protection Law.

### Dashboard

![Dashboard](assets/screenshots/DashBoard%20Page.png)
An interactive dashboard presenting an overview of the analysis results through four key visualizations:

Overall Compliance Status: Shows the ratio of compliant versus non-compliant texts.
Violation Type: Shows the distribution of detected PDPL violation categories.
Violations Over Time: Shows the daily trend of detected violations over time.
Frequency of Detected Violations: Shows the frequency of each detected violation type.

### History

![History](assets/screenshots/History%20Page.png)
A history page for reviewing previous compliance analyses.

## Future Work

Future improvements may include:

* Proactive prediction of compliance risks before violations occur
* Enhanced explainability using Large Language Models (LLMs)
* Real-time and adaptive recommendations instead of static rule-based recommendations
* Larger and more diverse real-world training data
* Expanded multilingual support

## Project Team

* Shahad Mahrous
* Reham Alhmaidi
* Lama Alqahtani
* Lujain Alahmadi
* Joman Beyari

## Academic Project

This project was developed as a **Data Science graduation project at the University of Jeddah**.
