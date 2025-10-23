# 🧬 Protein Function Prediction using Deep Learning  
**Author:** [Tenika Powell](https://github.com/YOUR-USERNAME)  
**Tools:** Python, TensorFlow, Pandas, Biopython, Scikit-learn  

---

## 🧠 Overview
This project focuses on **predicting protein biological functions** (Gene Ontology terms) directly from amino acid sequences using machine learning.  
It was inspired by the **CAFA (Critical Assessment of Functional Annotation)** challenge, one of the hardest problems in bioinformatics.

Even with a simplified model, this project demonstrates the **end-to-end machine learning workflow** — from raw biological data to model deployment.

---

## ⚙️ Project Pipeline

### **1. Data Sources**
- `train_sequences.fasta` → Raw protein sequences  
- `train_terms.tsv` → Protein-to-GO term mapping  

Both files were merged via a shared `EntryID` and cleaned to remove invalid or empty sequences.

---

### **2. Preprocessing**
- Extracted amino acid frequencies as numerical features (20D vectors).  
- Encoded GO terms using `LabelEncoder`.  
- Scaled all features with `StandardScaler`.  
- Split dataset into training (80%) and testing (20%).  

---

### **3. Model Architecture**
Implemented using `TensorFlow` and `Keras`:

```python
Sequential([
    Dense(256, activation='relu', input_shape=(X.shape[1],)),
    Dropout(0.2),
    Dense(128, activation='relu'),
    Dropout(0.2),
    Dense(num_classes, activation='softmax')
])
Optimizer: Adam (lr=0.001)

Loss: Sparse Categorical Crossentropy

Metrics: Accuracy

Callback: EarlyStopping (patience=10)


| Metric              | Value          |
| ------------------- | -------------- |
| Epochs              | 150            |
| Test Accuracy       | **10.02 %**    |
| Validation Accuracy | ~12 %          |
| Dataset Size        | ~500K proteins |
| Classes             | 100+ GO terms  |

While 10% may seem modest, it reflects the difficulty of multi-class protein function prediction, where random chance is <1%.
This score shows the model learned real biological patterns from raw sequence data.


🔍 Key Learnings

✅ Merging and cleaning biological data (FASTA + TSV)
✅ Feature engineering for amino acid–based models
✅ Handling imbalanced multi-class datasets
✅ Implementing callbacks and early stopping in TensorFlow
✅ Understanding performance limits in complex biological ML tasks

🚀 Next Steps

Implement class weighting to balance rare GO terms

Add dipeptide composition (400D) features

Integrate ProtBERT embeddings for contextual representations

Deploy via FastAPI or Streamlit for live prediction

💬 Reflections

This project taught me that real-world data science isn’t about perfection — it’s about perseverance, problem-solving, and translating complexity into results.

Working with biological sequence data pushed me to understand both data engineering and deep learning at a deeper level.

My 10% accuracy represents a fully functional, scalable ML pipeline that can evolve with stronger embeddings and better balance.

🧾 Sample Output
✅ Combined data shape: (537027, 4)
✅ Model training complete (150 epochs)
🧾 FINAL TEST ACCURACY: 10.02%
✅ Results exported to predicted_go_terms.csv

📎 Connect with Me

💼 LinkedIn

🧑🏽‍💻 GitHub

✉️ Email: powell.tenika.n@gmail.com

“The data may be messy, but my model runs clean.” – Tenika Powell 🧬✨


---

## 🔥 Optional LinkedIn Caption

> 🧬 After weeks of debugging, cleaning, and tuning, I trained a full deep learning pipeline to predict protein functions from amino acid sequences.  
>  
> Merged real FASTA + GO term data, built a TensorFlow model, and optimized with early stopping.  
>  
> My final accuracy: **10.02%** — but the learning? **100%.**  
>  
> This project taught me how to merge bioinformatics and machine learning — one amino acid at a time.  
>  
> 🔗 Check it out on GitHub → [github.com/YOUR-USERNAME/protein-function-prediction](https://github.com/YOUR-USERNAME/protein-function-prediction)

---






