# **DualView BMI: AI-Based Body Mass Index Prediction from Facial Images**  

[//]: # ![BMI Prediction](https://your-image-link.com) *(Optional: Add a relevant image here)*  

## **Overview**  
**DualView BMI** is a regression-based model that predicts Body Mass Index (BMI) from facial images using **multi-view analysis**. By leveraging **deep learning for feature extraction** and **machine learning for regression**, this approach achieves high accuracy and generalizability.  

## **Key Features**  
✅ **Multi-View Analysis**: Utilizes both **front** and **side** profile images for improved accuracy.  
✅ **State-of-the-Art Feature Extraction**: Uses **MTCNN** for face detection and **FaceNet (InceptionResnetV1)** for feature extraction.  
✅ **Optimized Regression Model**: Employs **XGBoost** for robust BMI prediction.  
✅ **Scalable and Efficient**: Designed for **real-time health assessments** and **telemedicine applications**.  

## **Project Workflow**  

1. **Data Preprocessing**  
   - Face detection using **MTCNN**  
   - Image alignment and normalization  

2. **Feature Extraction**  
   - Extract deep facial features from both front and side profiles
   - 512 x 2 = 1024-dimensional embeddings via **FaceNet**  
   - Dimensionality reduction via **Principal Component Analysis (PCA)**  

3. **Regression Model Training**  
   - Compare **Linear Regression, Decision Trees, Random Forest, and XGBoost**  
   - Use **XGBoost** for final BMI prediction  

4. **Performance Evaluation**  
   - Evaluate using **Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), R² Score, and Pearson Correlation Coefficient (PCC)**  

## **Installation**  
To set up the environment and run the project, follow these steps:  

### **1. Clone the Repository**  
```bash
git clone https://github.com/yourusername/DualView-BMI.git
cd DualView-BMI
```

### **2. Install Dependencies**  
```bash
pip install -r requirements.txt
```

### **3. Run the Model**  
```bash
python main.py --input_folder ./data/images
```

## **Dataset**  
This project utilizes the **Illinois Department of Corrections (IDOC) Mugshot Dataset**, which includes **60,000 images** with height and weight metadata for BMI calculation.  

## **Results**  
| Method | Profile Used | MAE | RMSE | R² Score | PCC |
|--------|-------------|-----|------|----------|-----|
| Proposed (MTCNN + FaceNet + XGBoost) | Front & Side | **0.7019** | **2.0186** | **0.8464** | **0.9202** |
| Proposed (Front Only) | Front | 1.8062 | 2.5438 | 0.7562 | 0.8902 |

## **Comparison with Existing Methods**  
| Method | Profile Used | MAE | RMSE | R² Score | PCC |
|--------|-------------|-----|------|----------|-----|
| Viola-Jones + ResNet | Front | 3.4047 | 4.6341 | 0.2023 | 0.4922 |
| ResNet (Front & Side) | Front & Side | 3.1824 | 4.3180 | 0.2969 | 0.5679 |
| MobileNet V2 | Front | 2.71 | 13.71 | 0.51 | - |

The **proposed method significantly outperforms traditional approaches** in accuracy and reliability.  

## **Future Enhancements**  
🔹 **Expand Dataset Diversity** to improve generalization across ethnicities.  
🔹 **Optimize Model Efficiency** for mobile and real-time applications.  
🔹 **Integrate Multi-Modal Learning** by combining facial features with metadata for better predictions.  
