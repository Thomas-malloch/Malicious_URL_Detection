# Malicious_URL_Detection
Malicious URL Detection using CNN:

This project implements a character-level Convolutional Neural Network (CNN) to classify URLs as malicious or benign. The model learns directly from raw URL strings by encoding them as sequences of characters and applying deep learning techniques for multi-class classification.

Dataset
File: malicious_phish.csv

Features:
url – raw URL string
type – URL class (4 categories)
URLs are lowercased and processed at the character level.
Approach
Character Encoding
Each character is mapped to an integer index.
Unknown characters are mapped to <UNK>, padding uses <PAD>.

Padding:
URLs are padded or truncated to a fixed length of 250 characters.

Model Architecture:
Embedding layer (learned character representations)
1D Convolution layer
Global Max Pooling
Fully connected layers
Softmax output for 4-class classification

Training:
Optimizer: Adam
Loss: Sparse Categorical Crossentropy
Batch size: 256
Epochs: 5
Validation split: 20%

Model Architecture:
Embedding → Conv1D → GlobalMaxPooling1D → Dense → Softmax

Evaluation:
The model is evaluated on a held-out test set.

Metric: Accuracy:
Additional metrics (precision, recall, F1, ROC-AUC) are imported for future evaluation.

Requirements: Python 3.x, NumPy, Pandas, Matplotlib, scikit-learn, TensorFlow / Keras
Notes:
This is a character-level model, meaning no manual feature engineering is required.
CNNs are well-suited for detecting malicious patterns such as suspicious substrings and character sequences in URLs.
