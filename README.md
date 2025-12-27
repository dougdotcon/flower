# FlowerFL: A Friendly Federated Learning Framework

<p align="center">
  <a href="https://flower.ai/">
    <img src="https://flower.ai/_next/image/?url=%2F_next%2Fstatic%2Fmedia%2Fflower_white_border.c2012e70.png&w=640&q=75" width="140px" alt="FlowerFL Website" />
  </a>
</p>

<p align="center">
    <a href="https://flower.ai/">Website</a> |
    <a href="https://flower.ai/blog">Blog</a> |
    <a href="https://flower.ai/docs/">Docs</a> |
    <a href="https://flower.ai/conf/flower-summit-2022">Conference</a> |
    <a href="https://flower.ai/join-slack">Slack</a>
    <br /><br />
</p>

[![GitHub license](https://img.shields.io/github/license/adap/flower)](https://github.com/adap/flower/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/adap/flower/blob/main/CONTRIBUTING.md)
![Build](https://github.com/adap/flower/actions/workflows/framework.yml/badge.svg)
[![Downloads](https://static.pepy.tech/badge/flwr)](https://pepy.tech/project/flwr)
[![Slack](https://img.shields.io/badge/Chat-Slack-red)](https://flower.ai/join-slack)

## Overview

FlowerFL (`flwr`) is a comprehensive framework for building federated learning (FL) systems. The design philosophy of FlowerFL is guided by a commitment to flexibility and user accessibility:

- **Customizable**: Federated learning systems vary significantly based on the application. FlowerFL allows for a wide range of configurations to meet the specific requirements of any project.

- **Extendable**: Originating from academic research at the University of Oxford, the framework is built with extensibility in mind. Developers can override and extend components to create state-of-the-art systems.

- **Framework-Agnostic**: FlowerFL supports any machine learning framework, including PyTorch, TensorFlow, Hugging Face Transformers, PyTorch Lightning, scikit-learn, JAX, TFLite, fastai, MLX, XGBoost, Pandas, and raw NumPy.

- **Understandable**: The codebase is designed for maintainability, encouraging community contributions and making it easy for developers to understand the internal logic.

## Key Features

*   **Framework Agnostic**: Use your preferred stack (PyTorch, TensorFlow, JAX, etc.).
*   **Scalable**: Designed to handle thousands of clients efficiently.
*   **Secure**: Supports TLS encryption and authentication mechanisms.
*   **Extensible**: Easy to customize aggregation strategies and client behaviors.

## Installation

To install the Flower framework, use pip:

bash
pip install flwr


For specific framework integrations (e.g., PyTorch):

bash
pip install flwr[torch]


## Quickstart

Here is a minimal example of a Flower client:

python
import flwr as fl
import numpy as np

class FlowerClient(fl.client.NumPyClient):
    def get_parameters(self, config):
        return [np.zeros((1, 1))]

    def fit(self, parameters, config):
        # Local training logic here
        return parameters, 1, {}

    def evaluate(self, parameters, config):
        # Evaluation logic here
        return 0.0, 1, {}

fl.client.start_client(server_address="127.0.0.1:8080", client=FlowerClient())


## Documentation

For detailed documentation, tutorials, and best practices, visit [flower.ai/docs](https://flower.ai/docs/).

## Community

Join the Flower community on [Slack](https://flower.ai/join-slack) to ask questions and share your projects.