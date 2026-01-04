# Road Hazard Detection (Cracks & Potholes)
**File Name:** `Road_Hazard_Detection_Technical_Lead(S.M. Huzaifa Ali).ipynb`  
**Technical Lead:** Syed Muhammad Huzaifa Ali  
**Group:** [WS25-PR7]

## Project Overview:
This project presents a **Road Hazard Detection (Cracks & Potholes)** designed to automate road surface inspections. By combining Deep Learning (CNN) with a Rule-Based Meta-Learner, the system doesn't just identify hazards—it evaluates their severity to help engineers prioritize repairs.

## Dataset & Setup:
We utilize the **RDD-2022 (China_Urban subset)**. To ensure project synchronization, we use a standardized Google Drive workflow.

* **Source File:** Downloaded from Kaggle"https://www.kaggle.com/datasets/aliabdelmenam/rdd-2022/data", Once downloaded the file, first rename it to `rdd-2022.zip` from the original archive.zip before uploading on Google Drive.
* **Storage:** Hosted on Google Drive for seamless Colab integration.
* **Preprocessing:** Automated extraction, path synchronization, and hazard-focused image cropping.

## Technical Architecture
The system follows a three-tier logic structure:
1.  **The Brain (CNN):** A **ResNet-18** model handles pattern recognition to classify "Normal," "Crack," or "Pothole."
2.  **The Measurement (Meta-Learner):** An OpenCV module calculates the **Area** and **Aspect Ratio** of detected hazards.
3.  **The Decision (Rule Engine):** A logic layer that fuses the CNN confidence with physical dimensions. For example, it classifies a 'Pothole' as 'Severe' only if the geometric area exceeds 5,000 pixels.

## Instructions to Reproduce
1.  **Data Placement:** Place your `rdd-2022.zip` file in the root directory of your Google Drive.
2.  **Open Notebook:** Launch `Road_Hazard_Detection_Technical_Lead(S.M. Huzaifa Ali).ipynb` in Google Colab.
3.  **Mount Drive:** Run the initialization cells to link your Drive. The script is pre-set to target `/content/drive/MyDrive/rdd-2022.zip`.
4.  **Run Experiment:** Execute all cells.
    * **Training:** 10 Epochs with real-time validation (Cell 7).
    * **Evaluation:** Confusion Matrix and Classification Reports (Cell 8).
    * **Inference:** Batch processing and CSV generation (Cell 12).

## Key Research Outcomes
* **RQ1-RQ3:** Established baseline CNN performance on the China_Urban dataset and motivated a hybrid architecture by analyzing geometric features and rule-based severity mapping for improved interpretability and robustness.
* **RQ4:** Compared CNN-only and hybrid models using confusion matrices, demonstrating reduced class confusion and more consistent hazard classification in the hybrid approach.
* **RQ5:** Demonstrated explainability-driven “Maintenance Intelligence” by visualizing how the model differentiates between cosmetic cracks and structurally significant potholes.


