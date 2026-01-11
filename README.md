# AI-Confusion-Matrix-Cpp
Confusion Matrix and Evaluation Metrics in Python
# Confusion Matrix and Evaluation Metrics (Python)
## Project Description
This project evaluates a binary classification model using a confusion matrix
and calculates accuracy, precision, recall, and F1-score.

# Confusion Matrix and Evaluation Metrics in Python

# Random dataset (Actual vs Predicted labels)
actual = [1, 0, 1, 1, 0, 1, 0, 0, 1, 0]
predicted = [1, 0, 0, 1, 0, 1, 1, 0, 1, 0]

TP = TN = FP = FN = 0

for i in range(len(actual)):
    if actual[i] == 1 and predicted[i] == 1:
        TP += 1
    elif actual[i] == 0 and predicted[i] == 0:
        TN += 1
    elif actual[i] == 0 and predicted[i] == 1:
        FP += 1
    elif actual[i] == 1 and predicted[i] == 0:
        FN += 1

print("Confusion Matrix")
print("----------------")
print("TP:", TP, "FP:", FP)
print("FN:", FN, "TN:", TN)

accuracy = (TP + TN) / (TP + TN + FP + FN)
precision = TP / (TP + FP)
recall = TP / (TP + FN)
f1_score = 2 * (precision * recall) / (precision + recall)

print("\nEvaluation Metrics")
print("------------------")
print("Accuracy :", accuracy)
print("Precision:", precision)
print("Recall   :", recall)
print("F1-Score :", f1_score)

