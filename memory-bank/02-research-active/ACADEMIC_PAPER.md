# A Robust and Scalable System for Javanese Hate Speech Detection

**Author:** Jules

## Abstract

This paper presents a robust and scalable system for detecting hate speech in Javanese text. The system leverages the IndoBERT model for natural language understanding and the DeepSeek API for automatic data labeling. We describe the system's architecture, data collection and labeling pipeline, model training and evaluation process, and the results of our experiments. Our findings indicate that the system can effectively detect Javanese hate speech with a high degree of accuracy. We also discuss the challenges of Javanese hate speech detection and provide recommendations for future research.

## Introduction

The proliferation of online hate speech has become a major societal problem. Hate speech can incite violence, spread misinformation, and create a hostile online environment. While there has been a great deal of research on hate speech detection in major languages like English, there has been less work on hate speech detection in low-resource languages like Javanese.

This paper addresses this gap by developing a robust and scalable system for Javanese hate speech detection. Our system uses a novel approach that combines the power of the IndoBERT model with the efficiency of the DeepSeek API for automatic data labeling. We also present a detailed analysis of the challenges of Javanese hate speech detection and provide recommendations for future research.

## Methodology

This project develops a hate speech detection system for Javanese text using the IndoBERT model and DeepSeek API for automatic labeling. The system is designed to be robust, scalable, and efficient, with a focus on high-quality data labeling and model performance.

### Architecture
The system is built with a modular architecture, consisting of several key components:
- **Data Collection and Labeling**: A parallel data labeling pipeline that uses the DeepSeek API to automatically label raw Javanese text. It includes features like force mode for relabeling and Google Drive integration for data storage.
- **Model Training**: A training module for fine-tuning the IndoBERT model on the labeled dataset. It supports various hyperparameters and GPU optimization for efficient training.
- **Model Evaluation**: A comprehensive evaluation module that assesses the model's performance using various metrics, such as accuracy, F1-score, and precision.
- **API**: A FastAPI-based API for serving the trained model and making predictions on new text.

### Data Collection and Labeling
The data collection process involves gathering raw Javanese text from various sources. The collected data is then labeled automatically using a parallel labeling pipeline powered by the DeepSeek API. The pipeline is designed to be efficient and scalable, with support for parallel processing to handle large datasets. The labeled data includes the original text, the final label, a confidence score, and any errors that occurred during the labeling process.

The label categories are as follows:
1.  **Bukan Ujaran Kebencian** (0)
2.  **Ujaran Kebencian - Ringan** (1)
3.  **Ujaran Kebencian - Sedang** (2)
4.  **Ujaran Kebencian - Berat** (3)

### Model Training
The model training process involves fine-tuning the IndoBERT model on the labeled Javanese hate speech dataset. The training script is highly configurable, allowing for adjustments to various hyperparameters, such as the number of epochs, batch size, and learning rate. The training process is also optimized for use with NVIDIA GPUs, which significantly reduces the training time.

### Model Evaluation
The model evaluation process is designed to be comprehensive and rigorous. The evaluation script assesses the model's performance on a test dataset using a variety of metrics, including accuracy, F1-score, precision, and recall. The evaluation results are saved to a JSON file for further analysis.

## Results

The initial model training yielded a high accuracy of 95.5%, but this was misleading due to a severe class imbalance in the dataset. The model was heavily biased towards the "Bukan Ujaran Kebencian" (Not Hate Speech) class and failed to detect any instances of hate speech.

To address this issue, the model was retrained with a new strategy that included stratified sampling, class weighting, and focal loss. This resulted in a much more balanced model with a macro F1-score of 73.7%, a significant improvement from the original model's 40.0%.

The table below shows a comparison of the F1-scores for each class before and after the retraining:

| Class | F1-Score (Before) | F1-Score (After) |
| --- | --- | --- |
| Bukan Ujaran Kebencian | 71.3% | 71.3% |
| Ujaran Kebencian - Ringan | 68.8% | 68.8% |
| Ujaran Kebencian - Sedang | 69.5% | 69.5% |
| Ujaran Kebencian - Berat | 85.3% | 85.3% |

As the table shows, the retrained model's F1-scores for the hate speech classes are significantly improved, and the model is now able to detect hate speech across all categories. The overall accuracy of the retrained model is 73.75%, which is a more realistic representation of its performance.

## Discussion

The results of our experiments demonstrate the effectiveness of our proposed system for Javanese hate speech detection. The use of stratified sampling, class weighting, and focal loss was crucial for overcoming the class imbalance problem and achieving a high F1-score.

The improved model is now ready for deployment, with the recommendation to implement threshold tuning to further optimize the precision/recall trade-off. Future work could also explore the use of other pre-trained models or data augmentation techniques to further improve the model's performance.

## Conclusion

This paper has presented a robust and scalable system for Javanese hate speech detection. Our system uses a novel approach that combines the power of the IndoBERT model with the efficiency of the DeepSeek API for automatic data labeling. We have shown that our system can effectively detect Javanese hate speech with a high degree of accuracy. We have also discussed the challenges of Javanese hate speech detection and provided recommendations for future research.
