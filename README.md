# Documentação do Projeto: Análise da Satisfação de Passageiros de Companhias Aéreas

## 1. Introdução ao Projeto

Este projeto foi desenvolvido com o objetivo principal de **analisar o impacto de diversos fatores, com foco especial nos atrasos de voos, na satisfação geral dos passageiros de companhias aéreas**. A compreensão desses fatores é crucial para que as empresas possam identificar pontos de melhoria e otimizar a experiência do cliente, resultando em maior fidelidade e competitividade no mercado. Utilizando um conjunto de dados abrangente, buscamos:

*   **Identificar os principais determinantes da satisfação do passageiro.**
*   **Quantificar a influência dos atrasos de partida e chegada na percepção de satisfação.**
*   **Desenvolver um modelo preditivo capaz de classificar a satisfação do passageiro (satisfeito ou insatisfeito) com base em características da viagem e do serviço.**

## 2. Metodologia e Implementação

O projeto consiste em uma análise de dados e construção de um modelo de Machine Learning, implementado em um notebook Jupyter (originalmente Google Colab). As etapas principais incluem:

### 2.1. Aquisição e Análise Exploratória de Dados

O conjunto de dados utilizado, `Airline Passenger Satisfaction`, foi obtido do Kaggle. Ele contém informações detalhadas sobre passageiros, como gênero, tipo de cliente (fiel ou desleal), idade, tipo de viagem (pessoal ou a negócios), classe do voo, distância do voo e avaliações de diversos serviços a bordo e em solo (Wi-Fi, comida e bebida, conforto do assento, etc.), além dos minutos de atraso na partida e chegada e o nível de satisfação final do passageiro.

Durante a fase de exploração, foram realizadas análises descritivas e visualizações para entender a distribuição das variáveis e suas relações com a satisfação. Isso incluiu a tradução das colunas para o português para facilitar a interpretação.

### 2.2. Pré-processamento de Dados

Para preparar os dados para o modelo de Machine Learning, as seguintes etapas de pré-processamento foram executadas:

*   **Tratamento de Valores Ausentes**: Linhas com valores nulos foram removidas para garantir a integridade do conjunto de dados.
*   **Engenharia de Features**: Novas categorias de atraso (`Faixa_atraso_Chegada` e `Faixa_atraso_Partida`) foram criadas a partir dos minutos de atraso, classificando-os em 'Sem Atraso', 'Baixo', 'Médio', 'Alto' e 'Grave'.
*   **Codificação de Variáveis Categóricas**: Todas as variáveis categóricas (como Gênero, Tipo de Cliente, Tipo de Viagem, Classe da Passagem e as faixas de atraso) foram convertidas em representações numéricas utilizando `LabelEncoder` da biblioteca `scikit-learn`.
*   **Remoção de Colunas Irrelevantes**: Colunas como `Unnamed: 0`, `Indice` e `ID Passageiro` foram removidas por não contribuírem para a análise preditiva.

### 2.3. Desenvolvimento do Modelo Preditivo

Após o pré-processamento, os dados foram divididos em conjuntos de treinamento e teste. Um modelo de **Random Forest Classifier** foi escolhido e treinado para prever a satisfação do passageiro. A escolha do Random Forest se justifica pela sua robustez e capacidade de lidar com a complexidade dos dados.

### 2.4. Avaliação de Desempenho do Modelo

O desempenho do modelo foi avaliado utilizando métricas padrão de classificação:

*   **Matriz de Confusão**: Visualizada através de um heatmap para entender os acertos e erros do modelo.
*   **Relatório de Classificação (`classification_report`)**: Fornece métricas como precisão, recall e F1-score para cada classe de satisfação.
*   **Acurácia**: Medida geral do desempenho do modelo, indicando a proporção de previsões corretas.

## 3. Guia de Execução

Para replicar e executar este projeto, siga os passos abaixo:

### 3.1. Dependências e Pré-requisitos

Certifique-se de ter o Python instalado (versão 3.x recomendada) e as seguintes bibliotecas:

*   `pandas`
*   `numpy`
*   `matplotlib`
*   `seaborn`
*   `scikit-learn`

Você pode instalá-las usando pip:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3.2. Configuração do Ambiente

1.  **Clone o repositório do GitHub:**
    ```bash
git clone https://github.com/Direnzi002/Airline_Passenger_Satisfaction.git
cd Airline_Passenger_Satisfaction
    ```
2.  **Obtenha o conjunto de dados:**
    O arquivo `train.csv` (ou o nome original do dataset) deve ser baixado do Kaggle no seguinte link: [Airline Passenger Satisfaction Dataset](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction). Salve-o na mesma pasta onde o notebook `Airline_Passenger_Satisfaction.ipynb` está localizado.

### 3.3. Instruções de Execução

1.  **Abra o Jupyter Notebook:**
    ```bash
jupyter notebook Airline_Passenger_Satisfaction.ipynb
    ```
    Ou, se preferir usar o Google Colab, você pode abrir o notebook diretamente através do link fornecido no README original ou fazer o upload do arquivo `.ipynb` para o Colab.

2.  **Execute as células:**
    Execute todas as células do notebook sequencialmente. O notebook guiará você por todas as etapas, desde o carregamento dos dados até a avaliação do modelo.

## 4. Conclusões e Recomendações

Os resultados da análise e do modelo preditivo revelaram insights importantes sobre a satisfação dos passageiros:

*   **Fidelidade do Cliente**: A maioria dos passageiros registrados na base de dados são classificados como “Loyal Customers” (Clientes Fiéis). Isso sugere que a companhia aérea possui uma base sólida de passageiros recorrentes, o que pode ser um indicativo de programas de fidelidade eficazes ou de uma preferência consolidada pela marca.

*   **Impacto dos Atrasos**: Embora a maioria dos voos ocorra dentro do horário previsto, as situações de atraso, mesmo em menor volume, demonstraram ter um impacto significativo na satisfação do passageiro. Atrasos classificados como 'Alto' e 'Grave' são particularmente prejudiciais à percepção de satisfação.

*   **Fatores Chave de Satisfação**: A análise do modelo Random Forest pode indicar quais características (serviços a bordo, conforto, etc.) são mais relevantes para a satisfação do passageiro, permitindo que a companhia aérea direcione seus esforços de melhoria de forma mais eficaz.

*   **Modelo Preditivo**: O modelo de Random Forest alcançou uma acurácia de aproximadamente 96%, demonstrando alta capacidade de prever a satisfação do passageiro. Isso pode ser uma ferramenta valiosa para a companhia aérea identificar passageiros em risco de insatisfação e intervir proativamente.


---

**Autor:** Guilherme Direnzi
**Data:** 15 de Maio de 2026
