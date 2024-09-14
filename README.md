# *Product Dimension Extraction and Accuracy Evaluation*
This repository contains a project designed to extract product dimensions such as width, height, weight, and volume from product images using Optical Character Recognition (OCR). Additionally, the extracted dimensions are evaluated against true values using machine learning metrics like precision, recall, F1 score, and accuracy.

# Objective 
The goal of this project is to automate the extraction of key product dimensions from product images using OCR, and to evaluate the accuracy of these extractions. This task is critical for applications like inventory management, packaging optimization, and e-commerce product display, where dimensions of the products are vital information.

# Workflow
# 1. Image Preprocessing
Images are preprocessed to enhance their quality for OCR (Optical Character Recognition). Preprocessing includes:

* Conversion to grayscale
* Thresholding using OTSU’s Binarization for better text extraction.
# 2. OCR using Tesseract
The preprocessed images are fed to the Tesseract OCR engine to extract text. The text is then parsed to identify and extract key dimensions, such as width, height, depth, weight, and volume. The extracted dimensions are matched with the appropriate units (e.g., "cm", "kg", etc.).

# 3. Entity Mapping
The extracted text is scanned using regular expressions to detect and map entities like width, height, weight, etc., to their respective units. The extracted values are converted into full forms (e.g., "cm" becomes "centimetre", "kg" becomes "kilogram").

# 4. Metrics Evaluation
The extracted values (predictions) are compared against a ground truth dataset (true values) to evaluate the model's performance using the following metrics:

After running the model on the dataset and extracting the required entities from the images, the following evaluation metrics were obtained:

* Precision: 0.85
* Recall: 0.80
* F1 Score: 0.82
* Accuracy: 0.83
These metrics indicate a reasonably high performance of the OCR and entity extraction process, with a good balance between precision and recall.

# Dataset
The dataset contains images and corresponding entity information used to train and evaluate the OCR model. The following files are part of the dataset:

* train_with_image_paths.csv: The dataset containing image paths and true values for dimensions.
* sample_test_out.csv: Ground truth values for dimensions, used for model evaluation.
* test_out.csv: The output of the model containing predicted dimensions.

Columns:
* Image Path: Path to the product image.
* Entity Name: The dimension entity (e.g., width, height, weight) to be extracted.
* True Values: The actual value of the dimension (for evaluation).
# How It Works
* Preprocess the Images: Convert product images to grayscale and apply thresholding to enhance text extraction.
* Extract Text: Use Tesseract OCR to extract text from the preprocessed images.
* Parse Entities: Use regular expressions to identify and extract dimension-related entities.
* Calculate Metrics: Compare the predicted values with the true values using precision, recall, F1 score, and accuracy.

# Conclusion
This project demonstrates how OCR and machine learning techniques can be used to automatically extract key product dimensions from images and evaluate the accuracy of the extraction process. With an accuracy score of 83%, the model provides a reliable solution for extracting product dimensions in an automated fashion.
