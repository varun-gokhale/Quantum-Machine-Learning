# Quantum-Machine-Learning
This repository deals with the implementation of Quantum Computing in the field of Machine Learning. The Qiskit library from IBM is used to build the model. This repository deals with creating Quantum ML models in two ways.
  1. By using CircuitQNN
  2. By using VQC (Varational Quantum Classifier)


### Configurations
You will require an environment to run Jupyter notebook. All the needed libraries are mentioned in the notebook itself and also inline magic function is used to install those libraries.


### Quantum Machine Learning

Quantum Machine learning is the integration of quantum algorithms within machine learning programs. The most common use of the term refers to machine learning algorithms for the analysis of classical data executed on a quantum computer.

The folowing are the methods described in the Notebook to model the Classification task.

  #### 1. Classification with a CircuitQNN
  
  In this context, it is shown how a CircuitQNN can be used for classification within a NeuralNetworkClassifier. The CircuitQNN is expected to return d-dimensional    probability vector as output, where d denotes the number of classes. Sampling from a QuantumCircuit automatically results in a probability distribution and we just need to define a mapping from the measured bitstrings to the different classes. For binary classification we use the parity mapping.
  
  #### 2. Variational Quantum Classifier (VQC)
  
  The VQC is a special variant of the NeuralNetworkClassifier with a CircuitQNN. It applies a parity mapping (or extensions to multiple classes) to map from the bitstring to the classification, which results in a probability vector, which is interpreted as a one-hot encoded result. By default, it applies this the CrossEntropyLoss function that expects labels given in one-hot encoded format and will return predictions in that format too.

### Dataset

The dataset is taken from the kaggle repository. The problem statement deals with predicting the quality of Milk using the given set of features. The dataset contains following features.

  1. PH Value
  2. Temperature
  3. Taste
  4. Odor
  5. Fat
  6. Turbidity
  7. Color
  8. Grade

The Grade is considered as the Target Variable. The task is to Classify the Grade of Milk, given the rest other features.


### Workflow

The scope of this repository is to show how Quantum Computing can be used to model Machine Learning Tasks. Taking Cost and availability of Quantum processing Units (QPUs) into consideration, This repository deals with running codes on Simulator. Qasm Simulator is used for this purpose, However there are various Cloud services which gives you the Quantum hardware to run your code in a real time QPU.

Next, if you see the Target variable, There are three categories into which the quality of Milk can be classified. So, for the sake of simplicity only Two categories that is Grade high and Grade low are taken into the consideration. However, by using VQC, Multi-class Classification can also be performed.

Next task is to choose the number of Qbits needed to build the Quantum Circuit. The number of Qbit is equal to the number of Input features in the dataset. Since there are total 7 Input features, So we have used 7 Qbits to build the Circuit

![circuit_image](https://user-images.githubusercontent.com/48384752/190922456-5ae111c3-230d-487f-b18d-f419a42223e5.png)

Both the Techniques are shown in the Notebook to build the model. You can compare both the model on the basis of their classification reports.
