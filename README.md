# ML_BarePass Machine Learning Assignment

This repository contains the implementation of my Machine Learning assignment, including data preprocessing, model training, evaluation, and analysis.

## Folder Structure

```
ml-course/
├── README.md                   # Project overview, setup instructions, and course info
├── requirements.txt            # Python dependencies
├── .gitignore                 # Specify files/folders to ignore
├── notebooks/                 # Jupyter notebooks for assignments and experiments
│   ├── assignment1/
│   │   ├── exploration.ipynb
│   │   └── submission.ipynb
│   ├── assignment2/
│   └── final_project/
│
├── data/                      # Dataset directory
│   ├── raw/                   # Original, immutable data
│   ├── processed/             # Cleaned and preprocessed data
│   └── external/              # External source data
│
├── src/                       # Source code
│   ├── __init__.py
│   ├── data/                 # Data processing scripts
│   │   ├── __init__.py
│   │   ├── make_dataset.py
│   │   └── preprocess.py
│   │
│   ├── features/             # Feature engineering scripts
│   │   ├── __init__.py
│   │   └── build_features.py
│   │
│   ├── models/               # Model training and prediction scripts
│   │   ├── __init__.py
│   │   ├── train_model.py
│   │   └── predict_model.py
│   │
│   └── visualization/        # Visualization scripts
│       ├── __init__.py
│       └── visualize.py
│
├── models/                    # Saved model files
│   ├── trained/              # Trained model artifacts
│   └── experiments/          # Experimental model versions
│
├── reports/                   # Generated analysis reports
│   ├── figures/              # Generated graphics and figures
│   └── final_project/        # Final project documentation
│
└── tests/                    # Unit tests
    ├── __init__.py
    ├── test_data.py
    └── test_models.py 
```

## Requirements

This project requires Python and several external libraries. The dependencies are listed in `requirements.txt`. Ensure you have Python installed before proceeding.

## Installation

```sh
# Clone the repository
git clone https://github.com/ThanhPhan14062003/ML_BarePass.git
cd ML_BarePass

# Install the required dependencies
conda create --name ml_barepass python=3.9
conda activate ml_barepass
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install -r requirements.txt
```

## Model Descriptions

This project implements multiple machine learning models, each with unique characteristics and applications:

### 1. SimpleMLP (Multi-Layer Perceptron)
The **SimpleMLP** is a fully connected neural network that serves as a deep learning baseline. It consists of:
- **Input Layer**: Accepts the input features.
- **Hidden Layer**: A single hidden layer with 128 neurons, using ReLU activation for non-linearity.
- **Output Layer**: A fully connected layer that maps to the number of output classes.
- **Training**: Uses cross-entropy loss and an optimizer (such as Adam or SGD).
- **Use Case**: Suitable for tasks requiring deep learning-based feature representation.

### 2. Decision Tree Classifier
The **Decision Tree Model** is a classic non-parametric supervised learning algorithm:
- **Algorithm**: Uses `sklearn.tree.DecisionTreeClassifier` with Gini impurity or entropy as the criterion.
- **Tree Structure**: Recursively splits features to create a hierarchy of decision nodes.
- **Training**: Learns rules based on training samples without requiring feature scaling.
- **Output**: Provides class predictions and probability estimates.
- **Use Case**: Useful for interpretable models and datasets with non-linear decision boundaries.

### 3. Naive Bayes Classifier
The **Naive Bayes Model** is a probabilistic classifier based on Bayes' Theorem with an independence assumption:
- **Algorithm**: Uses `sklearn.naive_bayes.GaussianNB`, assuming that feature distributions follow a Gaussian (normal) distribution.
- **Training**: Computes class-conditional probabilities and priors from training data.
- **Output**: Predicts classes based on the highest posterior probability.
- **Use Case**: Works well for high-dimensional datasets and text classification.

### 4. Hidden Markov Model (HMM)
The **HMM Model** is a sequence-based model that learns hidden state transitions:
- **Emission Network**: Uses an MLP to model emission probabilities (likelihood of observing input given a hidden state).
- **Transition Matrix**: A learnable matrix that represents transition probabilities between states.
- **Initial Probabilities**: Learnable start probabilities for sequence initialization.
- **Training**: Uses Negative Log-Likelihood (NLL) loss and optimizes transition/emission parameters.
- **Use Case**: Ideal for sequence prediction tasks like speech recognition and part-of-speech tagging.

### 5. Bayesian Network Model
The **Bayesian Network Model** is a probabilistic graphical model that incorporates uncertainty in learning:
- **Bayesian Layers**: Instead of fixed weights, the model learns a distribution over the weights (mean and variance).
- **Reparameterization Trick**: Samples weights from a Gaussian distribution to perform uncertainty estimation.
- **Output**: Produces log-softmax probabilities for classification.
- **Training**: Uses Negative Log-Likelihood (NLL) loss and optimizes both mean and variance of the weights.
- **Use Case**: Useful for uncertainty-aware classification tasks and Bayesian deep learning applications.


## Usage

```sh
# Preprocess the data (Just run in the first time) and train, explore on following notebook:
notebooks/assignment1/exploration.ipynb

# If you have already processed data, you can skip the first part of above implementation or run this file:
notebooks/assignment1/submission.ipynb

# Evaluate the model
python src/evaluate.py
```

## Results

All logs, metrics, and plots generated from the training and evaluation process will be stored in the `results/` folder.

## License

This project is for educational purposes.
