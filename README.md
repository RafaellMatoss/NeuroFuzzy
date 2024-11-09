# NeuroFuzzy

## Descrição do Projeto:
O objetivo deste projeto é treinar e utilizar um modelo neuro-fuzzy para prever a velocidade de um ventilador a partir de variáveis climáticas. A partir de uma base de dados simulada de temperaturas e umidades, o modelo ANFIS aprende a relação entre essas variáveis e a velocidade do ventilador, permitindo que futuras previsões sejam feitas de forma precisa.

O projeto é dividido em duas etapas:
* Treinamento: o modelo ANFIS é treinado usando uma base de dados de temperaturas e umidades e, em seguida, os parâmetros são salvos para uso posterior.
* Predição: os parâmetros treinados são carregados para que o modelo realize previsões em novos dados, sem a necessidade de retraining.


## Estrutura do Projeto:
O projeto possui duas partes principais:

* Bloco de Treinamento e Salvamento dos Parâmetros
Treina o modelo ANFIS utilizando dados de entrada (temperatura e umidade) e calcula o erro médio quadrático (MSE) a cada 10 épocas.
Após o treinamento, os parâmetros do modelo (médias, sigmas, e pesos) são salvos em um arquivo .pkl para futura utilização na etapa de predição.

* Bloco de Predição e Avaliação:
Carrega os parâmetros treinados do modelo e usa novos dados de entrada para realizar previsões.
Exibe os resultados comparando a velocidade esperada e a velocidade prevista.
Apresenta um gráfico comparativo entre os valores esperados e os valores preditos.



## Modelo:
O projeto usa um modelo ANFIS (Adaptive Neuro-Fuzzy Inference System) com as seguintes características:
* Funções de Pertinência Fuzzy: Gaussianas são usadas para modelar a relação entre temperatura, umidade e velocidade, proporcionando uma transição suave entre as regras.
* Regras Fuzzy: três regras fuzzy foram configuradas para representar diferentes faixas de temperatura e umidade.
* Treinamento: o modelo utiliza o algoritmo de backpropagation para ajustar seus parâmetros fuzzy (médias e desvios) e os pesos das regras, com uma taxa de aprendizado de 0.01.

O modelo é implementado com uma classe Python (ANFIS) que permite tanto o treinamento quanto a inferência.


## Descrição dos Dados:
Os dados são simulados para representar uma variação típica de temperatura e umidade:

* Temperatura: valores variando entre 20°C e 40°C.
* Umidade: valores variando entre 30% e 90%.
* Velocidade do Ventilador: é calculada usando a fórmula velocidade = 2.5 * temperatura + 0.5 * umidade, servindo como rótulo (target) para o modelo ANFIS.
* Essa simulação fornece uma base adequada para treinar o modelo e avaliar sua capacidade de generalização.


## Pré-processamento:
O pré-processamento é realizado na forma de uma combinação das variáveis de entrada (temperatura e umidade) em um array de características (X). A saída esperada (velocidade) é mantida em um array de rótulos (y). Esse formato de dados permite ao modelo ANFIS calcular as funções de pertinência fuzzy e ajustar os pesos das regras para otimizar as previsões.


## Métricas e Avaliação:
Métricas e Avaliação:
Erro Médio Quadrático (MSE): o MSE é utilizado durante o treinamento para monitorar o desempenho do modelo. A cada 10 épocas, o MSE é calculado e exibido para avaliar a redução de erro ao longo do tempo.
Avaliação Gráfica: na etapa de predição, as velocidades esperadas e preditas são visualizadas em um gráfico, permitindo uma inspeção visual da precisão das previsões.
