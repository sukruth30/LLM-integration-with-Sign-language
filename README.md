# LLM Integration with Sign Language Recognition (SLR)

## Introduction
Sign Language Recognition (SLR) plays a crucial role in bridging communication gaps between the hearing and deaf or hard-of-hearing communities. According to the World Health Organization, over 466 million people have disabling hearing loss globally, many of whom rely on sign language as their primary mode of communication.

This project aims to enhance SLR by combining **Random Forest Classifiers** and a **Large Language Model (LLM)**. The system recognizes sign language letters and converts them into coherent sentences, addressing the challenges of producing meaningful translations and overcoming regional sign language variations.

## Dataset
The dataset comprises sign language gestures, focusing on individual letters and numbers. Each class contains 100 images, resulting in 18,000 images across 36 classes (26 alphabets and 10 numbers).

### Dataset Overview:
| Data Type | Classes | Images |
| --------- | ------- | ------ |
| Alphabets | 26      | 13,000 |
| Numbers   | 10      | 5,000  |

## Methodology

### 1. Data Preprocessing and Feature Extraction
The **MediaPipe Hand Tracking** solution was used to extract features (x and y coordinates of 21 hand landmarks), producing a 42-dimensional feature vector for each gesture. These extracted coordinates were stored in a CSV file for further use.

### 2. Machine Learning Model
The **Random Forest Classifier** was chosen to recognize sign language letters. Random Forest uses ensemble learning by training multiple decision trees and selecting the most frequent prediction for classification. It is robust, handles high-dimensional data well, and is resistant to overfitting, making it an ideal choice for this application.

### 3. Sentence Formation Using LLM
After recognizing sign language letters, the system forms meaningful sentences using the **Gemma-7b-it LLM** via an API request. The LLM converts the sequence of recognized letters into coherent sentences.

## Architecture
The system follows a three-stage process:
1. **Feature Extraction** using MediaPipe.
2. **Letter Prediction** using Random Forest.
3. **Sentence Formation** using LLM (Gemma-7b-it).

![System Architecture](D:\NITT\Architecture.png)

## Results and Evaluation
The model was evaluated using the following metrics:
- **Confusion Matrix**
- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**

### Confusion Matrix:
![Confusion Matrix](D:\NITT\Confusion_matrix.png)

The Random Forest model achieved high accuracy in classifying sign language letters and numbers. The combination of the Random Forest model and LLM provided contextually correct sentences for seamless communication.

## Technologies Used
- **MediaPipe** for hand tracking and feature extraction.
- **Random Forest Classifier** for sign language letter recognition.
- **Gemma-7b-it LLM** for generating meaningful sentences from recognized letters.
- **Python** for development.
- **Flask** for backend API integration.

## How to Run the Project
1. Clone the repository:
    ```bash
    git clone https://github.com/your-username/your-repo-name.git

  
## Future Enhancements
- **Real-Time Recognition**: Enable live sign language translation via webcam.
- **Incorporate More Gestures**: Expand the dataset to include additional hand gestures and regional sign languages.
- **Mobile Compatibility**: Optimize the system for mobile and resource-constrained devices.

## Conclusion
This project demonstrates an effective integration of machine learning and LLMs to improve communication for deaf and hard-of-hearing individuals. By utilizing a Random Forest classifier for letter recognition and an LLM for sentence generation, the system produces meaningful translations that significantly enhance user interaction.


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
