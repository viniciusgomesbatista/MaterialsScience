# Análise e Previsão da Resistência à Compressão do Concreto

Este projeto visa analisar e prever a resistência à compressão do concreto utilizando técnicas de aprendizado de máquina com a biblioteca PyCaret. A análise envolve a manipulação de dados, exploração de correlações e construção de modelos preditivos.

## Índice

- [Introdução](#introdução)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Instalação](#instalação)
- [Descrição do Projeto](#descrição-do-projeto)
  - [Carregamento e Preparação dos Dados](#carregamento-e-preparação-dos-dados)
  - [Análise Exploratória dos Dados](#análise-exploratória-dos-dados)
  - [Divisão dos Dados em Treino e Teste](#divisão-dos-dados-em-treino-e-teste)
  - [Configuração e Treinamento de Modelos](#configuração-e-treinamento-de-modelos)
  - [Avaliação do Modelo](#avaliação-do-modelo)
  - [Salvamento do Modelo](#salvamento-do-modelo)
- [Próximos Passos](#próximos-passos)
- [Como Contribuir](#como-contribuir)
- [Licença](#licença)

## Introdução

Este projeto utiliza dados de componentes do concreto para prever sua resistência à compressão. O objetivo é aplicar técnicas de aprendizado de máquina para criar um modelo preditivo eficiente.

## Tecnologias Utilizadas

- **Python**: Linguagem de programação utilizada.
- **Pandas**: Biblioteca para manipulação de dados.
- **NumPy**: Biblioteca para operações matemáticas.
- **Scikit-learn**: Biblioteca para dividir os dados em treino e teste.
- **Seaborn e Matplotlib**: Bibliotecas para visualização de dados.
- **PyCaret**: Biblioteca para automação de machine learning.
- **Google Colab**: Ambiente para execução do código.

## Instalação

Para executar este projeto, siga os passos abaixo:

1. Clone este repositório:
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    ```
2. Instale as dependências:
    ```bash
    pip install pandas numpy scikit-learn seaborn matplotlib pycaret
    ```

## Descrição do Projeto

### Carregamento e Preparação dos Dados

Os dados são carregados a partir de um arquivo CSV armazenado no Google Drive. As colunas são renomeadas para facilitar a interpretação.

```python
import pandas as pd

df = pd.read_csv('/content/drive/MyDrive/Estudos/Pós Graduação/Dados/concrete_data.csv')
df.rename(columns={
    'Cement':'Cimento', 'Blast Furnace Slag':'Escória de alto-forno', 'Fly Ash':'Cinzas volantes',
    'Water':'Água', 'Superplasticizer':'Superplastificante', 'Coarse Aggregate':'Agregado Grosso',
    'Fine Aggregate':'Agregado Fino', 'Age':'Idade', 'Strength':'Resistência à compressão'
}, inplace=True)
