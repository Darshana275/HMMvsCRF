# HMMvsCRF

This project implements a speech recognition system using Hidden Markov Models (HMM) and Conditional Random Fields (CRF). The system is trained and evaluated on audio datasets containing spoken words.


HMM-based Speech Recognition:

1. Trains Gaussian HMM models for each word class.
   
2. Uses MFCC features for sequence classification.
 
3. Outputs accuracy and AUC metrics.

CRF-based Speech Recognition:

1. CRF for feature refinement and logistic regression for classification.

2. Combines frame-level features to improve sequence-level predictions.

3. Outputs accuracy, precision, recall, F1 score, and AUC metrics.

Prerequisites


Ensure Python 3.8+ is installed and use the dependencies listed in requirements.txt:

pip install -r requirements.txt

Dependencies include:

librosa

numpy

scikit-learn

hmmlearn

matplotlib

sklearn-crfsuite


Training and Testing with HMM

Run hmm.py to train HMM models and evaluate them:

python hmm.py

Key outputs:

Accuracy of the model on test data.

AUC-ROC and AUC-PR curves.

Recognized word for a test .wav file.

Modify the test_audio_file variable in hmm.py to test single audio files.

Training and Testing with CRF

Run crf.py to train CRF and logistic regression models and evaluate them:

python crf.py

Key outputs:

Accuracy, precision, recall, and F1 score.

AUC-ROC and AUC-PR curves.

Recognized word for a test .wav file.

Modify the test_audio_file variable in crf.py to test single audio files.

Evaluating and Comparing Models

Use evaluate.py to compare HMM and CRF models.

Outputs include metrics such as accuracy, precision, recall, and F1 score for both models.

python evaluate.py

Results

HMM Performance

Accuracy: ~79%

AUC-ROC: 0.81

AUC-PR: 0.78

CRF Performance

Accuracy: ~85%

AUC-ROC: 0.88

AUC-PR: 0.85

Conclusion:

The comparison between the HMM-based and CRF-based speech recognition systems reveals key insights into their performance:

HMM-based Model: The HMM approach provides a solid foundation for speech recognition, yielding an accuracy of ~79%. While it achieves reasonable AUC scores (AUC-ROC: 0.81, AUC-PR: 0.78), it is slightly limited in its ability to achieve higher performance compared to CRF, especially in precision and recall metrics.

CRF-based Model: The CRF model outperforms HMM, with an accuracy of ~85%. It shows notable improvements in both AUC-ROC (0.88) and AUC-PR (0.85), reflecting its superior ability to handle complex sequential data by leveraging frame-level features and logistic regression for classification. CRF's ability to refine features and improve sequence-level predictions likely contributes to its enhanced performance.
