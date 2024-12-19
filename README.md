# **Celebrity Image Classification** 🌟

![Project Preview](https://github.com/Naveennnkumar-Bit/Celeb_Image_classifier/blob/main/Preview.png)  <!-- Preview Image Path -->

## **Project Overview**

This project involves building a machine learning model to classify images of celebrities into different categories based on their faces. The project includes multiple steps: data collection, data cleaning, feature engineering, model training, and deployment to a web server. It also features a front-end UI for image uploading and classification. The project will be helpful for learners to understand how to build and deploy an image classification model in a corporate environment. 🖼️

## **Technologies Used** ⚙️

- **Python**: Core language for implementing machine learning models and image preprocessing.
- **Flask**: Lightweight Python web framework to deploy the model as an API.
- **OpenCV**: Image processing library used for face detection and preprocessing.
- **NumPy**: Used for handling arrays and image data manipulation.
- **Scikit-learn**: Used for machine learning algorithms (e.g., SVM, Grid Search CV).
- **HTML/CSS/JavaScript**: Front-end technologies used to build the UI for image uploading and classification.
- **PyWavelets**: For wavelet transformation to enhance feature extraction.
- **Joblib**: For model serialization (saving the trained model).

---

## **Steps Involved** 🛠️

### **1. Data Collection and Cleaning**

- **Data Collection**: Images of celebrities were scraped from Apify.
- **Face Detection**: OpenCV's Haar Cascade classifier is used for detecting faces and eyes in images to filter out poor-quality images.
- **Data Cleaning**: Images with obstructed faces or poor visibility are discarded to maintain dataset integrity. Around 80-90% of this process is automated with Python scripts, while the remaining images undergo manual inspection.
- **Wavelet Transformation**: Applied to images to extract meaningful features such as eyes, nose, and lips, and then combine the transformed images with raw images for model training.

### **2. Model Training** 🎓

- **Support Vector Machine (SVM)** is chosen as the initial model for image classification.
- **Data Scaling**: StandardScaler is used to normalize the features.
- **Model Evaluation**: Grid Search CV is used to tune hyperparameters for SVM, Random Forest, and Logistic Regression.
- **Performance**: SVM and Logistic Regression are evaluated on accuracy, with SVM performing well in cross-validation and Logistic Regression showing higher test accuracy.
- **Final Model**: The best-performing model (SVM) is chosen for deployment.

### **3. Model Export** 💾

- The trained model is saved using **Joblib** in a pickle file (`saved_model.pickle`), along with a JSON file for class mappings.

---

## **Server and API Implementation** 🌐

### **Flask Server Setup**

1. **Flask Server** is set up to handle image classification requests.
2. **API Endpoints**: A test endpoint (`/hello`) is created to ensure the server is functioning.
3. **Image Classification Endpoint**: A route is implemented to handle image classification requests. Images are uploaded as base64 strings or via a URL.

### **Image Classification**

- **Image Preprocessing**: Images are decoded from base64 format, resized, and processed using OpenCV.
- **Model Prediction**: The processed image is passed through the trained model to get predictions.
- **Result Handling**: The server returns predictions along with probability scores for each class.

---

## **UI Development** 🖥️

### **User Interface Features**

1. **Drag-and-Drop Upload**: Users can drag and drop images for classification.
2. **Classification Button**: Triggers the classification process.
3. **Result Display**: The UI shows the classification result and the highest match score among multiple candidates.
4. **Error Handling**: Proper feedback is given if an image can't be classified.

### **Back-End Communication**

- **AJAX Calls**: The UI communicates with the Flask server using jQuery for HTTP POST requests.
- **Base64 Encoding**: Images are sent to the server as base64 encoded strings.

---

## **Deployment Options** 🚀

- **Amazon EC2**, **Google Cloud**, and **Heroku** are suggested platforms for deploying the project.
- Users are encouraged to follow deployment tutorials and adapt them for image classification models.

---


