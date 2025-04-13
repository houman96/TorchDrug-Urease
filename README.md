# Generative Modeling of Urease Inhibitors with TorchDrug's GCPN and RGCN

This project focuses on the generation of novel urease inhibitors by leveraging the Graph Convolutional Policy Network (GCPN) and Relational Graph Convolutional Network (RGCN) models provided by [TorchDrug](https://torchdrug.ai/). The approach integrates reinforcement learning techniques to optimize molecular properties, aiming to discover potential therapeutic agents against urease-related diseases.

## Overview

- **Objective**: Generate novel, chemically valid urease inhibitors with optimized properties.
- **Dataset**: Curated urease inhibitors from [BindingDB](https://www.bindingdb.org/).
- **Models Used**:
  - **GCPN**: Graph Convolutional Policy Network for goal-directed molecular graph generation.
  - **RGCN**: Relational Graph Convolutional Network for capturing relational information in molecular graphs.
- **Training Criteria**:
  - **PPO**: Proximal Policy Optimization for reinforcement learning.
  - **NLL**: Negative Log-Likelihood for supervised learning.
- **Hardware**: Trained on NVIDIA RTX 2060 GPU.
- **Training Details**:
  - **Epochs**: 1000
  - **Batch Size**: 16
  - **Duration**: Approximately 8 hours

## Methodology

### Data Preparation

The dataset comprises validated urease inhibitors extracted from BindingDB. These molecules were preprocessed to ensure compatibility with TorchDrug's modeling requirements.

### Installation

This project was developed and tested using:

- **TorchDrug version**: 0.2.1  
- **CUDA version**: 11.6.2 
- **Python version**: 3.8.19 
- **Environment manager**: Conda

To replicate the environment, please use the provided `environment.yml` file.

### Model Architecture

The neural network architecture consists of 8 layers, each with 256 neurons. The RGCN model serves as the backbone for feature extraction, while the GCPN model facilitates the generation of novel molecular graphs.

### Training Procedure

The training process involves a combination of supervised and reinforcement learning:

- **Supervised Learning**: Utilizing NLL to guide the model in generating valid molecular structures.
- **Reinforcement Learning**: Employing PPO to optimize specific molecular properties, such as drug-likeness and synthetic accessibility.

The training was conducted over 1000 epochs with a batch size of 16, utilizing an NVIDIA RTX 2060 GPU, and completed in approximately 8 hours.

## Results

The trained model successfully generated novel urease inhibitor candidates exhibiting desirable chemical properties. These molecules demonstrate potential for further experimental validation and development. The backbone was selected from our previous paper. The results gave insight on the subtitution for designing potent urease inhibitors.

## TorchDrug Integration

This project extensively utilizes TorchDrug's capabilities for molecular graph generation and property optimization. For more information on TorchDrug's molecule generation tutorial, visit the [official documentation](https://torchdrug.ai/docs/tutorials/generation.html).

## References

- Kazemzadeh, et al. "Design, Synthesis, and Biological Evaluation of Novel Urease Inhibitors." *ACS Omega*, 2022. [https://pubs.acs.org/doi/full/10.1021/acsomega.2c01028](https://pubs.acs.org/doi/full/10.1021/acsomega.2c01028)
- TorchDrug Molecule Generation Tutorial: [https://torchdrug.ai/docs/tutorials/generation.html](https://torchdrug.ai/docs/tutorials/generation.html)
- BindingDB Information: [https://www.bindingdb.org/bind/info.jsp](https://www.bindingdb.org/bind/info.jsp)

## License

This project is licensed under the Apache License 2.0.
