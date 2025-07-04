# projeto-puc-analise-de-dados-e-boas-praticas
MVP do sprint de análise de dados e boas práticas. 
Análise de Dados de OEE (Overall Equipment Effectiveness)
Este projeto tem como objetivo analisar um conjunto de dados de OEE (Overall Equipment Effectiveness) de diversas máquinas semelhantes. Através da exploração e modelagem dos dados, busca-se compreender o comportamento de atributos chave como dia da semana, OEE, IE (Índice de Eficiência) e IQ (Índice de Qualidade), bem como os eventos de parada, para desenvolver um modelo preditivo.

🚀 Problema e Objetivos
O problema central abordado neste projeto é o entendimento do comportamento de performance de máquinas industriais com o objetivo de prever o OEE. O dataset contém informações de diversas máquinas (Alpha, Beta, Gamma, Delta, Epsilon, Zeta, Eta, Theta, Iota, Kappa, Lambda, Sigma, Omega) e eventos de parada, além de indicadores de desempenho.

Hipóteses Iniciais
Para guiar a análise, foram formuladas as seguintes hipóteses:

Existe alguma correlação entre o OEE e o dia da semana?

Há alguma correlação entre o OEE e os eventos de parada?

Existe algum padrão visual comum entre os equipamentos?

Tipo de Problema
Este projeto aborda um problema de classificação supervisionada. O objetivo é, com base em um conjunto de variáveis como dia da semana, turno, máquina e histórico de eventos, prever o OEE do equipamento para o dia seguinte.

📊 Seleção e Descrição dos Dados
O conjunto de dados foi coletado de um sistema de execução de manufatura (MES). Os nomes das máquinas foram anonimizados e alguns eventos foram agrupados. É importante notar que o dataset contém problemas de dados intencionais, mantidos para fins de aprendizado e exercício de conhecimentos em tratamento de dados.

Atributos do Dataset
O dataset apresenta os seguintes atributos:

Data: Data do registro.

Turno: Turno de operação.

PEvento: Evento de parada com a maior duração.

FreqPEvento: Frequência de ocorrência do PEvento.

DuracaoPEvento: Duração total do PEvento.

SEvento: Evento de parada com a segunda maior duração.

FreqSEvento: Frequência de ocorrência do SEvento.

DuracaoSEvento: Duração total do SEvento.

Somatoral: Tempo total acumulado em todos os eventos.

Dds: Dia da semana em código numérico.

Maquina: Identificador único da máquina.

Meta: Meta de OEE estabelecida.

Dds2: Dia da semana em formato descritivo.

ID: Índice de Disponibilidade do equipamento. Relaciona o tempo disponível de produção (desconsiderando finais de semana e eventos não punitivos) com os eventos de parada não planejada.

IE: Índice de Eficiência. Obtido comparando o tempo padrão de produção com o tempo produzido.

IQ: Índice de Qualidade. Obtido comparando a produção total com a produção com defeito.

OEE: Overall Equipment Effectiveness (Eficiência Geral dos Equipamentos). Calculado pela multiplicação de ID x IQ x IE.

Observações Importantes sobre os Dados:

Os índices (ID, IE, IQ) são calculados com base em apontamentos manuais feitos pelos operadores em um sistema MES.

Eventos de parada são registrados manualmente pelos operadores.

O sistema MES é um software para apontamento de eventos e ordens de produção. O operador deve iniciar uma ordem de produção no início do processo e apontar as peças produzidas no final.

💡 Conclusões da Análise
A análise dos dados de OEE revelou diferenças significativas de comportamento entre as máquinas, mesmo pertencendo a um grupo semelhante. Fatores como a produção de ordens de produção distintas e a atuação de diferentes operadores impactam as variáveis de Eventos, ID, IE e IQ, resultando em padrões individualizados.

As hipóteses iniciais foram avaliadas da seguinte forma:

Há alguma correlação entre o OEE e o dia da semana?

Não. Não foi observada correlação, mesmo ao analisar máquinas individualmente.

Existe alguma correlação entre o OEE e os eventos de parada?

Baixa. Embora alguns eventos (como "quebra de máquina") possam impactar significativamente o ID e, consequentemente, o OEE, sua natureza aleatória impede uma forte correlação.

Há algum padrão visual entre os equipamentos?

Não. Os comportamentos individuais de cada equipamento se sobressaem em relação a qualquer similaridade de grupo.

Em suma, a análise sugere que cada equipamento possui um comportamento único e deve ser tratado individualmente para uma modelagem mais eficaz.

Próximos Passos Sugeridos (Caso a Acurácia do Modelo Não Seja Adequada)
Se o modelo de previsão não apresentar a acurácia desejada, as seguintes ações poderiam ser consideradas:

Aumento da Base de Dados: Expandir o dataset para mais de 2 anos pode ajudar o modelo a identificar padrões sazonais ou de longo prazo que não foram capturados.

Modelagem Segmentada: Avaliar a possibilidade de criar modelos menores para prever o ID e o IE separadamente, e então multiplicar os resultados para obter o OEE final.

Análise de Operadores: Investigar se a presença de diferentes operadores nas máquinas influencia os resultados, visto que operadores mais experientes podem apresentar um IE superior.
