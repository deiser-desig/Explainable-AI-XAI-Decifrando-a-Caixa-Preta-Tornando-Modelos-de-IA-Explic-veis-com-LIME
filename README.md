# Decifrando-a-Caixa-Preta-Tornando-Modelos-de-IA-Explic-veis-com-LIME

CONTEXTUALZAÇÃO DO PROBLEMA E DEFINIÇÃO DO OBJETIVOS:

Soluções baseadas em Inteligência Artificial estão cada vez mais presentes no setor financeiro, especialmente em modelos preditivos para concessão de crédito. No entanto, mesmo com altos índices de acurácia, modelos considerados "caixa preta" como florestas aleatórias ou redes neurais despertam desconfiança entre clientes, gerentes e órgãos regulatórios, pois não deixam claro os motivos por trás das decisões.
Neste projeto, o objetivo é desenvolver um modelo de classificação de risco de crédito usando o dataset Statlog German Credit Data e aplicar a técnica LIME Local Interpretable Model-agnostic Explanations para explicar, de forma local e individualizada, quais atributos influenciaram mais nas decisões do modelo principalmente nos casos de negação de crédito.

EXPLICAÇÃO DO MODELO PREDITIVO ESCOLHIDO: 

Random Forest: Para a tarefa de classificação binária bom ou mau risco de crédito, optei por utilizar o algoritmo Random Forest Classifier, uma técnica de ensemble baseada em árvores de decisão. Motivos da escolha: Lida bem com variáveis numéricas e categóricas, reduz overfitting em comparação com uma única árvore, oferece boas métricas de desempenho e robustez em problemas reais, suporta extração de importância de variáveis, o que complementa as explicações do LIME. O modelo foi treinado após pré-processamento adequado dos dados incluindo encoding de variáveis categóricas e normalização, quando necessário e avaliado com métricas como acurácia, precisão, recall e F1-score.

DISCUSSÃO INTERPRETATIVA SOBRE AS EXPLICAÇÕES GERADAS PELO LIME:

Interpretação Local: Após treinar o modelo, foi utilizado a biblioteca Lime para entender melhor as decisões individuais. O Lime funciona aproximando o comportamento do modelo em torno de uma instância específica por meio de um modelo interpretable como regressão linear.
Exemplo de aplicação: Para um cliente que teve o crédito negado, o Lime revelou que as principais variáveis que influenciaram negativamente a decisão foram: Histórico de crédito ruim, alta duração do empréstimo, baixa capacidade de pagamento, tipo de conta com pouco tempo de abertura.
Por outro lado, para um cliente aprovado, o Lime destacou: Bom histórico de crédito, emprego estável, idade acima de 30 anos, valor do crédito solicitado abaixo da média.
Essas explicações locais foram visualizadas em gráficos gerados automaticamente pelo Lime, que mostraram de forma clara e intuitiva os fatores mais relevantes para cada caso.

REFLEXOES SOBRE AS LIMITAÇÕES, A IMPORTANCIA DA INTERPRETABILIDADE E COMO AS EXPLICAÇÕES CONTRIBUIRAM PARA A COMPREENSÃO DO MODELO:

Apesar de poderoso, o Lime apresenta algumas limitações importantes: Explicações locais podem variar entre instâncias muito próximas, depende da amostragem sintética feita no entorno da instância analisada, não oferece visão global do comportamento do modelo, pode ser sensível a ruídos ou correlações espúrias nos dados.
Ainda assim, a interpretabilidade proporcionada pelo Lime é extremamente valiosa em contextos de alta responsabilidade, como o crédito bancário.
Ela permite: Aumentar a confiança do cliente nas decisões, justificar tecnicamente o motivo de uma negação, atender exigências regulatórias ex: LGPD, GDPR, identificar potenciais viéses ou injustiças no modelo.

CONCLUSÂO:

Com o uso do Lime, conseguimos abrir a caixa preta do modelo de classificação e entender por que ele tomou determinadas decisões, essa capacidade de explicação local é fundamental não apenas para transparência, mas também para ética e justiça algorítmica, sendo uma etapa indispensável em aplicações reais de IA no setor financeiro.

