# Good Seed - Age Verification Model Using Computer Vision

## Project Description

Good Seed, a supermarket chain, aims to ensure compliance with alcohol laws by preventing sales to underage customers. To support this, they are exploring whether Data Science can help verify customers’ ages using computer vision applied to photos captured at checkout counters.

This project focuses on building and evaluating a model that predicts a person's age from facial images, aiding in automated age verification during alcohol purchases.

---

## Project Goals

- Develop a computer vision model to estimate a person's real age from facial images.
- Evaluate the model's performance using Mean Absolute Error (MAE).
- Determine if the model can support legal compliance efforts in supermarkets.

---

## Dataset

- **Images:** ~7,591 facial photos stored in `/datasets/faces/final_files/`
- **Labels:** `labels.csv` containing two columns:
  - `file_name`: Image filename
  - `real_age`: Actual age of the person

---

## Methodology

1. **Exploratory Data Analysis (EDA):**
   - Dataset contains 7,591 labeled images with no missing values.
   - Age distribution ranges from 1 to 100 years, with a mean of 31 and a positive skew.
   - Sample images inspected; preprocessing includes grayscale conversion and horizontal flipping for augmentation.

2. **Data Handling:**
   - Images are loaded using a generator (`ImageDataGenerator`) to optimize memory and computation.
   - Avoided loading all images at once due to large dataset size.

3. **Model Training:**
   - Trained for 20 epochs on a GPU platform.
   - Used MAE as the key evaluation metric to measure average absolute error between predicted and actual ages.
   - Applied augmentation (e.g., horizontal flip) and grayscale preprocessing.

4. **Evaluation:**
   - Initial Epoch 1: Training MAE = 7.43, Validation MAE = 8.49
   - Best Epoch 17: Training MAE = 3.22, Validation MAE = 6.64
   - Final Epoch 20: Training MAE = 3.18, Validation MAE = 7.65
   - Noted a spike in validation MAE at epoch 12, possibly due to outliers or mislabeled data.
   - Early stopping around epoch 17 recommended for best validation performance.

---

## Results and Conclusions

- The model predicts ages with an average error under 7 years.
- Training improvements indicate learning progression, though some overfitting is evident from validation fluctuations.
- For customers near legal age thresholds, additional manual ID verification will be necessary.
- The model’s accuracy supports the use of computer vision as an aid in enforcing alcohol sale regulations.
- Other potential applications include:
  - Targeted advertising and content personalization
  - User identity verification
  - Fraud prevention

---

## Usage Notes

- Model training requires a GPU-enabled environment due to the size and complexity of image data.
- Further improvements could involve better augmentation, regularization, and hyperparameter tuning to reduce overfitting.

---

## Repository Structure

good-seed-age-verification/
├── datasets/
│ └── faces/
│ ├── final_files/ # Facial images
│ └── labels.csv # Age labels
├── notebooks/ # EDA and training notebooks
├── models/ # Saved trained models
├── scripts/ # Data processing and training scripts
└── README.md # Project documentation

yaml
Copy
Edit

---

## Acknowledgements

This project is part of an evaluation for Good Seed supermarket chain's compliance with alcohol laws using data science and computer vision.

