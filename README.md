# ⚖️ Legal_Compliance_Text_Classification

## 📌 Project Overview

This project focuses on **compliance classification of emails and disclosures** using **Large Language Models (LLMs)** with **Parameter-Efficient Fine-Tuning (PEFT)** and **Low-Rank Adaptation (LoRA)**.  

The dataset consists of **179 labeled examples** categorized into **four classes**:

- 🚫 **CAN-SPAM Violation** – Emails that violate CAN-SPAM Act requirements  
- ✅ **CAN-SPAM Compliant** – Emails that comply with CAN-SPAM Act  
- 🛡️ **CCPA Disclosure** – Proper disclosures under the California Consumer Privacy Act  
- ❌ **Non-Disclosure** – Inadequate or missing privacy notices  

---

## 🔄 Pipeline

1. 🧹 **Data Preprocessing** → Cleaning, formatting, preparing input (`dataset_preprocessing.ipynb`)  
2. 🏋️ **Model Training** → Fine-tuning LLM with LoRA + PEFT (`lora-peft-compliance-classification.ipynb`)  
3. 📊 **Evaluation & Predictions** → Testing on unseen data (`Test_Predictions.csv`)  

---

## 📊 Dataset Summary
**Total Examples**: 179  

- 🚫 CAN-SPAM Violation: **54**  
- 🛡️ CCPA Disclosure: **50**  
- ✅ CAN-SPAM Compliant: **40**  
- ❌ Non-Disclosure: **35**  

---

## 🛠️ Approach

1. 🔧 *Preprocessing*  
   - Standardized dataset  
   - Converted text + labels into machine-readable format  
   - Handled imbalance with stratified splitting  

2. 🤖 *Model Fine-Tuning*  
   - Pre-trained transformer (GPT-2) with LoRA adapters  
   - Applied **PEFT (LoRA)** to reduce training cost  
   - Tuned LoRA rank & scaling for efficiency vs. accuracy  

3. 📈 *Evaluation*  
   - Tested on hold-out set  
   - Predictions saved in `Test_Predictions.csv`  
   - Metrics: **Accuracy, Precision, Recall, F1-score per class**  

4. 🚀 *Deployment Ready*  
   - Fine-tuned model can classify **new emails or disclosures** into four categories  

---

## 📌 Results & Observations
- ⚡ **LoRA-PEFT** reduced GPU memory usage while maintaining strong performance  
- 🌍 Model generalizes well across compliance-related text despite limited dataset  
- ✅ Predictions show meaningful classification boundaries  

---

## 💡 Recommendations
- 📈 **Expand Dataset** → More compliance examples across industries/jurisdictions  
- ⚖️ **Class Balancing** → Oversampling / augmentation for underrepresented classes  
- 🤝 **Model Variants** → Try **Legal-BERT**, **GPT-Legal**, or domain-specific models  
- 📊 **Evaluation Metrics** → Use macro-F1 to handle imbalance  
- 🔗 **Deployment** → Wrap with **FastAPI / Flask API** for compliance monitoring tools  

---

## 🏁 Conclusion
This project demonstrates how **LoRA + PEFT** can **efficiently fine-tune LLMs** for compliance classification, making it suitable for **real-world regulatory monitoring** and **legal text analysis** with **limited resources**.

---
