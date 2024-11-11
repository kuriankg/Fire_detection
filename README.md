# Fire_detection
Fire Detection Model using Deep Learning
Objective: Build a deep learning model to detect and classify images of fire, non-fire, and smoke.

Data Preparation:

Images are organized into training and testing directories with three classes: fire, non-fire, and smoke.
Image dimensions are set to 150x150 pixels, with batch size at 32.
Data Augmentation:

Training data is augmented (rescaled, sheared, zoomed, horizontally flipped) to improve model robustness.
Testing data is only rescaled.
Data Generators:

ImageDataGenerators are created for both training and testing datasets with categorical class mode.
Model Architecture:

A Sequential CNN is designed with three convolutional layers and max pooling, followed by flattening.
Dense layers include a 512-unit hidden layer with ReLU activation, a dropout layer (0.5), and a final softmax layer for classification.
Model Compilation:

Compiled with Adam optimizer, categorical crossentropy loss, and accuracy as the evaluation metric.
Handling Corrupt Files:

A function (remove_corrupt_images) removes any corrupt images from both training and testing directories.
File Existence Verification:

A function (check_files_in_directory) ensures all required files exist in specified directories and removes any missing references.
Safe Data Generators:

A safe_data_generator function is defined to handle file errors dynamically, preventing training interruptions.
Model Training:

The model is trained on 8 epochs with safe generators, saving accuracy and loss metrics at each epoch.
Performance Visualization:

Plots for training and validation accuracy and loss are generated to evaluate model performance across epochs.
Model Saving:

The trained model is saved as fire_detection_model.h5 for future inference.
Model Evaluation:

Evaluated on the test data to determine final accuracy.
