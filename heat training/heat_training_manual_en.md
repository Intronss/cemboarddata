# Heat Training User Manual

## Introduction

Heat Training is a deep-learning-based regression model training module built on the TensorFlow/Keras framework. It supports customizable network architectures, optimizers, and loss functions, and is suitable for various regression prediction tasks.

## Data Preparation

### Data Format Requirements

- **File format**: Tab-separated text file (`.txt`)
- **Data layout**: The last column is the target value (y), and the preceding columns are feature values (X)
- **Example**:
  ```
  Feature1 Feature2 Feature3 Target
  1.2      3.4      5.6      7.8
  2.1      4.3      6.5      8.7
  ```

### File Upload

1. **Training file (required)**: File that contains the training data
2. **Test file (optional)**: If no test file is provided, the system will automatically split the training data into train/test sets according to the specified ratio

## Parameter Configuration

### Training Configuration

- **Training Name**: Name of the training task; all training-related files will be stored in a folder with this name.

### Basic Parameters

- **Test Size**: Proportion of data used as the test set (default: 0.2); used only when no separate test file is provided.
- **Skip Rows**: Number of rows skipped from the top of the file (default: 0).
- **Random State**: Random seed for reproducible train/test splitting (default: 0).
- **Batch Size**: Number of samples per training batch (default: 32).

### Learning Rate Parameters

- **Initial Learning Rate**: Learning rate at the start of training (default: 0.02).
- **Decay Steps Rate**: Ratio used to determine the decay steps for the learning rate (default: 20).
- **Decay Rate**: Factor by which the learning rate decays each time (default: 0.99).

### Model Parameters

- **Optimizer**: Optimizer options  
  - Adam (default)  
  - SGD  
  - Adagrad  
  - RMSprop  
  - Adadelta  
  - Nadam

- **Loss Function**: Loss function options  
  - MeanSquaredError (default, suitable for regression tasks)  
  - Huber  
  - Other loss functions

- **Number of Layers**: Number of hidden layers, from 1 to 9.

- **Epochs (Run)**: Total number of training epochs (default: 2000).

### Output Parameters

- **Output Epoch Interval**: Number of epochs between logging training information (default: 10).
- **Save Model Interval**: Number of epochs between saving model checkpoints (default: 100).

### Layer Configuration

The format for each layer is: `units + activation`.

- **units**: Number of neurons in the layer (integer).
- **activation**: Name of the activation function (e.g., `relu`, `sigmoid`, `tanh`).

**Examples**:  
- `64relu`: 64 neurons with ReLU activation.  
- `128sigmoid`: 128 neurons with Sigmoid activation.  
- `256tanh`: 256 neurons with Tanh activation.

## Output Files

- **train.txt**: Training data file (backup).  
- **test.txt**: Test data file (if provided).  
- **scaler.pkl**: Data scaler used for preprocessing inputs during prediction.  
- **Hyd_model.keras**: Final trained model file.  
- **model_epoch_*.keras**: Intermediate model checkpoints saved during training.  
- **parameters.json**: Configuration file for training parameters.  
- **trainout.txt**: Training output log.  
- **plot.txt**: Training and test losses recorded per epoch.  
- **plotstep.txt**: Training and test losses recorded by step (every 100 steps).

