# AI-Confusion-Matrix-Cpp
Confusion Matrix and Evaluation Metrics in C++
# Confusion Matrix and Evaluation Metrics (C++)

## Project Description
This project evaluates a binary classification model using a confusion matrix
and calculates accuracy, precision, recall, and F1-score.

## C++ Source Code

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<int> actual   = {1, 0, 1, 1, 0, 1, 0, 0, 1, 0};
    vector<int> predicted = {1, 0, 0, 1, 0, 1, 1, 0, 1, 0};

    int TP = 0, TN = 0, FP = 0, FN = 0;

    for (int i = 0; i < actual.size(); i++) {
        if (actual[i] == 1 && predicted[i] == 1)
            TP++;
        else if (actual[i] == 0 && predicted[i] == 0)
            TN++;
        else if (actual[i] == 0 && predicted[i] == 1)
            FP++;
        else if (actual[i] == 1 && predicted[i] == 0)
            FN++;
    }

    cout << "Confusion Matrix\n";
    cout << "TP: " << TP << " FP: " << FP << endl;
    cout << "FN: " << FN << " TN: " << TN << endl;

    double accuracy  = (double)(TP + TN) / (TP + TN + FP + FN);
    double precision = (double)TP / (TP + FP);
    double recall    = (double)TP / (TP + FN);
    double f1Score   = 2 * (precision * recall) / (precision + recall);

    cout << "Accuracy: " << accuracy << endl;
    cout << "Precision: " << precision << endl;
    cout << "Recall: " << recall << endl;
    cout << "F1-Score: " << f1Score << endl;

    return 0;
}
```
