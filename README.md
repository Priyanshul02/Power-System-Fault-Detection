⚡ Power System Fault Detection and Classification using IBM Watsonx AutoAI

📌 Overview
This project leverages IBM Watsonx AutoAI to build a machine learning model that can detect and classify power system faults in real time using electrical phasor data. It aims to improve fault identification accuracy and reduce response time, contributing to more stable and reliable power grid operations.


🧠 Problem Statement

In power distribution systems, faults such as line-to-ground (LG), line-to-line (LL), double line-to-ground (LLG), and three-phase (LLL) faults can cause significant disruption. Traditional methods of fault detection can be slow or error-prone. This project uses machine learning to automate and enhance the detection and classification of such faults based on voltage and current measurements.

✅ Objectives
- Classify power system conditions as **Normal**, **LG**, **LL**, **LLG**, or **LLL** faults.
- Train and deploy the model using **IBM Watsonx AutoAI** with zero manual coding.
- Provide an easy-to-integrate **REST API** for real-time prediction.
- Evaluate and rank different ML pipelines automatically.
  
🧰 Tools & Technologies
- **IBM Watsonx.ai Studio**
- **IBM AutoAI**
- **IBM Cloud Object Storage**
- **Watson Machine Learning**
- **Kaggle Dataset** (Voltage & Current Phasor Data)
- **JSON** for API testing

📁 Dataset
- **Source**: [Kaggle - Power System Faults Dataset](https://www.kaggle.com/datasets/ziya07/power-system-faults-dataset)
- **Description**: Includes labeled voltage and current phasor readings under normal and various fault conditions.

🔄 System Workflow
1. Create IBM Cloud project & Watsonx.ai instance
2. Upload dataset to Object Storage
3. Configure and run an **AutoAI experiment**
4. AutoAI selects best model pipeline
5. Deploy the model as a REST API
6. Test using JSON data input

## 🚀 Model Deployment
- **Model Type**: Auto-selected classifier (e.g., Random Forest, XGBoost)
- **Features**: Voltage and current phasors from phases A, B, C
- **Output**: Fault type (Normal, LG, LL, LLG, LLL)

🔌 Sample Input (JSON)
```json
{
  "input_data": [
    {
      "fields": ["Ia", "Ib", "Ic", "Va", "Vb", "Vc"],
      "values": [[12.3, 11.5, 13.1, 228.0, 232.5, 229.7]]
    }
  ]
}
