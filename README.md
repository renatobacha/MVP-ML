## Previsão do Campeão da Copa do Mundo FIFA 2026 com Machine Learning

Este projeto desenvolve um modelo preditivo para estimar o provável campeão da Copa do Mundo FIFA de 2026, utilizando um abordagem híbrida de Machine Learning com base em dados históricos de partidas.

## Objetivo

O objetivo principal é transformar o histórico de confrontos internacionais de seleções em insights preditivos. O modelo simula a estrutura do torneio (fase de grupos e mata-mata) para apontar a seleção com maior probabilidade estatística de se sagrar campeã.

## Metodologia

Adotamos uma estratégia em duas etapas:

## Módulo de Regressão: 

Prevê a quantidade de gols que cada time fará em uma partida específica, analisando o histórico de gols marcados e sofridos de cada seleção.
Módulo de Classificação: Prevê o resultado direto do confronto (Vitória, Empate ou Derrota) usando a diferença de ranking (simulada) e a expectativa de gols do módulo de regressão.
Com os modelos treinados, um simulador replica o regulamento da Copa do Mundo, desde a fase de grupos até a final, resolvendo empates com base na força histórica dos times.

## Dados e Pré-processamento

Dados: Histórico de partidas das Copas do Mundo, filtrando para o 'futebol moderno' (pós-1990).
Engenharia de Features: Criadas variáveis de desempenho acumulado (médias de gols marcados e sofridos) para cada seleção, simulando informações disponíveis antes de cada jogo.
Divisão Treino/Teste: Utilizada uma divisão temporal, treinando com dados de Copas anteriores a 2014 e testando com a Copa de 2014 para evitar vazamento de dados.
Pré-processamento: Pipeline com imputação de mediana (como segurança) e padronização das features numéricas.

## Modelos Utilizados

Baseline: Regressão Logística (Classificação) e Ridge (Regressão).
Candidatos: Random Forest e Gradient Boosting (para ambos, classificação e regressão).
Otimização: O modelo Gradient Boosting Classifier foi otimizado via GridSearchCV para melhorar o desempenho e estabilizar a variância.

## Resultado

O modelo final, um Gradient Boosting Classifier otimizado, demonstrou melhor desempenho em relação ao baseline na previsão de resultados de partidas. A simulação da fase de mata-mata da Copa do Mundo de 2026, utilizando a força de ataque e defesa das seleções, aponta para uma previsão de campeão baseada nas métricas históricas de resiliência e consistência.
