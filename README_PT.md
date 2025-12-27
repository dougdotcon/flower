# FlowerFL: Um Framework Amigável para Aprendizado Federado

<p align="center">
  <a href="https://flower.ai/">
    <img src="https://flower.ai/_next/image/?url=%2F_next%2Fstatic%2Fmedia%2Fflower_white_border.c2012e70.png&w=640&q=75" width="140px" alt="Website FlowerFL" />
  </a>
</p>

<p align="center">
    <a href="https://flower.ai/">Site</a> |
    <a href="https://flower.ai/blog">Blog</a> |
    <a href="https://flower.ai/docs/">Documentação</a> |
    <a href="https://flower.ai/join-slack">Slack</a>
    <br /><br />
</p>

[![GitHub license](https://img.shields.io/github/license/adap/flower)](https://github.com/adap/flower/blob/main/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/adap/flower/blob/main/CONTRIBUTING.md)
[![Downloads](https://static.pepy.tech/badge/flwr)](https://pepy.tech/project/flwr)

## Visão Geral

FlowerFL (`flwr`) é um framework completo para a construção de sistemas de aprendizado federado (AF). A filosofia de design do FlowerFL é baseada em flexibilidade e acessibilidade ao usuário:

- **Personalizável**: Sistemas de aprendizado federado variam significativamente de acordo com a aplicação. O FlowerFL permite uma ampla gama de configurações para atender às requisitos específicos de qualquer projeto.

- **Extensível**: Originado de pesquisas acadêmicas na Universidade de Oxford, o framework foi construído com foco na extensibilidade. Os desenvolvedores podem substituir e estender componentes para criar sistemas de ponta.

- **Independente de Framework**: O FlowerFL suporta qualquer framework de aprendizado de máquina, incluindo PyTorch, TensorFlow, Hugging Face Transformers, PyTorch Lightning, scikit-learn, JAX, TFLite, fastai, MLX, XGBoost, Pandas e NumPy puro.

- **Comprensível**: A base de código é projetada para manutenibilidade, incentivando contribuições da comunidade e facilitando o entendimento da lógica interna.

## Principais Recursos

*   **Independente de Framework**: Utilize sua stack preferida (PyTorch, TensorFlow, JAX, etc.).
*   **Escalável**: Projetado para lidar com milhares de clientes de forma eficiente.
*   **Seguro**: Suporta criptografia TLS e mecanismos de autenticação.
*   **Extensível**: Fácil de personalizar estratégias de agregação e comportamentos do cliente.

## Instalação

Para instalar o framework Flower, use o pip:

bash
pip install flwr


Para integrações específicas com frameworks (ex: PyTorch):

bash
pip install flwr[torch]


## Início Rápido

Aqui está um exemplo mínimo de um cliente Flower:

python
import flwr as fl
import numpy as np

class FlowerClient(fl.client.NumPyClient):
    def get_parameters(self, config):
        return [np.zeros((1, 1))]

    def fit(self, parameters, config):
        # Lógica de treinamento local
        return parameters, 1, {}

    def evaluate(self, parameters, config):
        # Lógica de avaliação
        return 0.0, 1, {}

fl.client.start_client(server_address="127.0.0.1:8080", client=FlowerClient())


## Documentação

Para documentação detalhada, tutoriais e melhores práticas, visite [flower.ai/docs](https://flower.ai/docs/).

## Comunidade

Junte-se à comunidade Flower no [Slack](https://flower.ai/join-slack) para fazer perguntas e compartilhar seus projetos.