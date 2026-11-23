Universidade de Brasília

Programa de Pós-Graduação em Estruturas e Construção Civil

Plano de Trabalho e Pesquisa • Doutorado

# Transferência adaptativa de aprendizado para prever a condição de superestruturas de pontes em redes com poucos históricos de inspeção

Wallas Borges Araújo

Área de concentração em Estruturas

Linha de pesquisa em Métodos Numéricos e Computacionais Aplicados à Engenharia (Estruturas)

Brasília, novembro de 2026

<!-- página -->

## 1. Introdução

Uma equipe de gestão de pontes precisa decidir quais estruturas merecem reavaliação técnica antes de conhecer o resultado da próxima inspeção. Duas pontes com a mesma nota atual podem apresentar trajetórias distintas. O material e a tipologia da superestrutura, a idade da obra, o intervalo previsto entre inspeções e o histórico de mudanças de nota ajudam a formular essa previsão. Em redes com poucos registros, há poucas oportunidades de observar transições para as condições de maior interesse.

Históricos de outras redes oferecem exemplos adicionais. Entretanto, o desempenho obtido na origem pode se perder no destino quando mudam as tipologias predominantes, as práticas de manutenção ou a atribuição das notas. A pesquisa irá prever a distribuição das possíveis notas da superestrutura na próxima inspeção registrada. O significado físico da nota é o da condição atribuída ao componente pelo procedimento de inspeção. A avaliação de capacidade resistente exigiria outras observações e outro modelo.

**Pergunta de pesquisa.** Em redes com poucos históricos locais, quanto peso deve receber a experiência de outras redes para prever a próxima nota da superestrutura, e em quais condições esse compartilhamento aumenta o erro?

**Hipótese.** Regular o peso externo segundo o erro ordinal observado em inspeções anteriores do destino e a incerteza dessa estimativa reduzirá a magnitude das perdas por transferência negativa, preservando parte dos ganhos quando as redes forem compatíveis. A hipótese será confrontada com previsões futuras em estados tratados como novos destinos.

## 2. Justificativa

Para o gestor, interessa reconhecer quando o histórico local já sustenta uma decisão e quando a informação externa melhora a interpretação de uma nota antiga. Para o PECC, a questão envolve modelar a evolução observada de um componente estrutural e quantificar os limites de um método computacional sob escassez de inspeções. O trabalho relaciona a previsão ao tipo de superestrutura e às condições sob as quais foi produzida a informação de campo. A avaliação por material e tipologia permitirá localizar eventuais perdas que uma média da rede encobriria.

<!-- página -->

## 3. Objetivos

**Objetivo geral.** Desenvolver e avaliar um método de transferência adaptativa para prever probabilisticamente a condição da superestrutura de pontes rodoviárias na próxima inspeção.

**Objetivos específicos**

1. Reconstruir históricos comparáveis por ponte, distinguindo novas inspeções, republicações e alterações cadastrais.
2. Estimar a contribuição dos dados externos por uma regra de ponderação sensível à incerteza do erro local.
3. Quantificar o benefício e a perda por transferência sob diferentes quantidades de dados locais, materiais e tipologias.
4. Avaliar o uso retrospectivo das previsões na triagem para reavaliação técnica e estabelecer os requisitos para testar o método em acervos brasileiros.

## 4. Revisão da literatura

Behrooz e Ilbeigi [1] modelaram a condição de pontes como uma variável ordinal e produziram previsões probabilísticas com históricos do inventário norte-americano. O caráter ordinal é decisivo para a engenharia. Prever uma categoria adjacente à observada tem implicações distintas de concentrar probabilidade em uma condição muito superior à registrada.

Chen, Yuan e Lin [2] desenvolveram transferência hierárquica entre nove jurisdições canadenses. O estudo contempla redes pequenas, heterogeneidade entre agências e atributos parcialmente ausentes. Esse é o antecedente direto para o compartilhamento entre gestores. A questão que motiva este projeto é quanto o desempenho em inspeções locais anteriores permite ajustar esse compartilhamento quando o alvo é uma nota ordinal futura e os episódios de piora são escassos.

Yao e colaboradores [3] estimam pesos de combinação de distribuições a partir do desempenho preditivo fora da amostra. Sua extensão hierárquica [4] admite pesos que variam com os dados. Esses trabalhos fundamentam dois comparadores fortes. A contribuição a testar é o valor incremental de penalizar a incerteza do ganho de transferência estimada por ponte, em uma avaliação temporal e regional de transições de condição. O desenho permite reconhecer uma combinação convencional como suficiente, caso produza desempenho equivalente.

<!-- página -->

## 5. Metodologia

### 5.1 População, dados e evidência preliminar

O estudo será longitudinal, retrospectivo e integralmente remoto. A fonte principal será o National Bridge Inventory (NBI), da Federal Highway Administration (FHWA). Os arquivos históricos no formato ASCII permitem trabalhar com uma convenção documental comum até 2025 [5, 6]. Cada estado representará uma rede de gestão para fins experimentais. A população elegível será composta por pontes rodoviárias com identificador recuperável e avaliação numérica da superestrutura em pelo menos duas datas distintas.

A unidade de previsão será o par de inspeções consecutivas observadas da mesma ponte. A chave longitudinal combinará estado e número da estrutura (itens 1 e 8). A data de inspeção, a frequência programada e a nota da superestrutura correspondem aos itens 90, 91 e 59. Os identificadores serão preservados como texto. Para cada previsão será adotado um corte na edição do inventário disponível naquela ocasião. O modelo usará a última nota conhecida, o histórico anterior, o intervalo programado, o material, a tipologia, a idade e o vão quando disponíveis. A data efetiva da inspeção seguinte será utilizada para localizar o desfecho e avaliar diferenças de horizonte.

**Piloto de viabilidade.** A leitura dos quatro arquivos de Delaware, de 2022 a 2025, encontrou respectivamente 872, 874, 872 e 874 registros. Considerando nota numérica e mês válido, 1.228 ocorrências repetiram uma combinação de estrutura e data já observada. Em 40 dessas ocorrências, a nota diferiu da versão anterior. Adotando a última ocorrência disponível para cada chave e data, 555 estruturas forneceram 784 pares de datas sucessivas. Houve 76 reduções, 77 aumentos e 631 permanências de nota. Essas contagens demonstram a possibilidade de construir o painel em um estado e dimensionam o desequilíbrio entre os desfechos. A origem das revisões e a cobertura em outros estados ainda exigem auditoria [5, 6].

Na análise principal serão excluídos pares com conflito de nota na mesma data ou indício de mudança de identidade da obra. A análise de sensibilidade repetirá a estimação com as revisões documentadas. Reconstruções identificáveis serão marcadas e os resultados examinados com e sem os intervalos correspondentes. Uma melhora de nota pode refletir reparo, variação de avaliação ou revisão de cadastro. A interpretação ficará limitada às mudanças registradas. Serão descritas também as pontes sem retorno observado, pois a frequência de inspeção pode estar associada à condição.

<!-- página -->

### 5.2 Modelagem e contribuição proposta

Em cada estado de destino, um modelo ordinal de transição fornecerá as probabilidades locais das notas futuras, condicionadas à última nota e aos atributos disponíveis. Um modelo da mesma família será ajustado com os estados de origem. O modelo local terá regularização para estabilizar as estimativas nas amostras pequenas. A combinação das duas distribuições será uma média ponderada, com peso externo entre zero e um. Em uma rede com modelos discordantes, esse peso determina quanto a previsão se afasta da experiência local.

A regra candidata usará previsões retrospectivas produzidas em ordem temporal dentro do conjunto de desenvolvimento. Para cada peso candidato, será calculada a diferença entre o erro da combinação e o erro do modelo local nos mesmos exemplos. A regra escolherá o peso que minimize a perda média acrescida de uma penalidade proporcional ao erro-padrão da diferença, estimado por reamostragem de pontes. Assim, o método precisará de evidência mais consistente para atribuir peso alto a uma origem cujo benefício varia muito entre estruturas. O peso zero estará entre os candidatos. A intensidade da penalidade será escolhida em redes de desenvolvimento tratadas alternadamente como destinos e congelada antes da avaliação externa. O desempenho dessa escolha constitui a hipótese metodológica da tese.

Para isolar o efeito da regulação serão comparados a persistência da última nota, o modelo local, o ajuste conjunto sem diferenciação regional, o modelo aplicado diretamente da origem, o compartilhamento hierárquico de parâmetros e a combinação que minimiza o erro médio sem penalidade. Um comparador de combinação hierárquica verificará se o ganho pode ser explicado pela estabilização convencional dos pesos [2–4]. Cada estratégia terá acesso ao mesmo conjunto local. A política para ausência completa de históricos será avaliada separadamente como previsão de origem, pois não há erro local observável para calibrar a regra.

<!-- página -->

### 5.3 Experimento e medida principal

Cada rodada reservará um estado como destino. Os anos iniciais fornecerão o histórico de desenvolvimento, um período posterior permitirá calibração local e as inspeções finais constituirão o teste. Dados dos estados de origem respeitarão a mesma data de corte. A escassez será simulada por subamostras de pontes locais com todos os seus registros elegíveis. Os tamanhos serão definidos a partir das contagens do piloto ampliado e fixados antes do teste. Uma avaliação adicional reservará pontes inteiras do destino para mensurar desempenho em estruturas novas. O uso de uma ponte já conhecida no teste temporal exigirá que todos os seus atributos tenham sido registrados antes da previsão.

O resultado principal será o Ranked Probability Score (RPS), calculado pela média, entre os limiares da escala, dos erros quadráticos entre a probabilidade acumulada prevista e o indicador acumulado observado. O escore preserva a ordem das notas e premia distribuições precisas. Quanto menor seu valor, melhor a previsão [7]. As perdas serão resumidas primeiro por ponte e depois por estado, atribuindo o mesmo peso às redes no resumo principal.

Para cada estado e orçamento de dados locais, haverá transferência negativa quando o RPS médio do método superar o do modelo local nas mesmas inspeções. Serão relatadas a frequência, a magnitude e a incerteza dessas diferenças pareadas. A calibração será examinada comparando a probabilidade prevista de queda da nota com a frequência observada de quedas. Os resultados incluirão contagens por faixa de probabilidade, material, tipologia e condição inicial. Células com poucos eventos terão interpretação descritiva. A hipótese perderá sustentação se a penalização aumentar o erro médio sem reduzir perdas nas redes mais afetadas, ou se o compartilhamento convencional produzir resultados equivalentes dentro da precisão observada.

<!-- página -->

### 5.4 Uso público e aplicação ao Brasil

A análise ilustrativa ordenará, a cada data de corte, as pontes elegíveis segundo a probabilidade prevista de piora. Com a mesma capacidade de revisão, a seleção será comparada com ordenações pela última nota e pela defasagem da última inspeção. A medida será a proporção de pioras posteriormente registradas que aparecia entre as pontes selecionadas. O benefício mensurável no estudo será a capacidade de localizar esses registros em uma revisão retrospectiva. A avaliação de redução de acidentes ou de custos de manutenção dependeria de um desenho prospectivo próprio.

O produto brasileiro será um protocolo para avaliar a aplicabilidade em acervos de obras de arte especiais. A ficha da DNIT 010/2024–PRO servirá de referência para documentar identificador, datas, tipologia, material, componente avaliado, critério de atribuição de nota e intervenções [8]. A correspondência entre escalas dependerá do significado técnico de cada classe. Com cadastro disponível, será estimada a cobertura dos atributos brasileiros nos dados de origem. Com inspeções sucessivas comparáveis e autorizadas, será feita avaliação externa temporal. Um inventário de outro país poderá cumprir esse mesmo papel se a documentação sustentar a equivalência do desfecho. O núcleo experimental utilizará arquivos públicos acessíveis a distância.

### 5.5 Cronograma e produtos

**Ano 1.** Revisão comparativa dos antecedentes, auditoria de múltiplos estados, formação do painel e registro prévio dos critérios de elegibilidade, partições e métricas. Produto previsto: dicionário e protocolo reproduzível de formação de pares de inspeções.

**Ano 2.** Ajuste dos modelos de referência, implementação da regra adaptativa em Python e experimentos de desenvolvimento. Produto previsto: implementação documentada com cálculo dos pesos e dos escores por ponte.

**Ano 3.** Avaliação em estados e períodos reservados, curvas de desempenho por disponibilidade local, comparação dos componentes e estudo das situações de transferência negativa. Produto previsto: artigo sobre o método e seus limites de aplicação.

**Ano 4.** Avaliação retrospectiva da triagem, protocolo de aplicação aos acervos brasileiros e síntese da tese. O acesso a históricos internacionais adicionais ou brasileiros permitirá ampliar a evidência de validade externa.

<!-- página -->

## 6. Referências bibliográficas

[1] BEHROOZ, H.; ILBEIGI, M. An ordinal autoregressive deep learning model for probabilistic prediction of bridge deterioration condition levels. Structure and Infrastructure Engineering, 2025. DOI 10.1080/15732479.2025.2571872.

[2] CHEN, W.; YUAN, A. X.-X.; LIN, P. Cross-jurisdictional collaborative deterioration modeling via hierarchical Bayesian transfer learning. Computer-Aided Civil and Infrastructure Engineering, v. 40, p. 6456–6474, 2025. DOI 10.1111/mice.70159.

[3] YAO, Y.; VEHTARI, A.; SIMPSON, D.; GELMAN, A. Using stacking to average Bayesian predictive distributions (with discussion). Bayesian Analysis, 2018. DOI 10.1214/17-BA1091.

[4] YAO, Y.; PIRŠ, G.; VEHTARI, A.; GELMAN, A. Bayesian hierarchical stacking: some models are (somewhere) useful. arXiv, 2021. Identificador 2101.08954.

[5] FEDERAL HIGHWAY ADMINISTRATION. National Bridge Inventory: download NBI ASCII files. Arquivos estaduais de Delaware, edições 2022–2025. www.fhwa.dot.gov/bridge/nbi/ascii.cfm.

[6] FEDERAL HIGHWAY ADMINISTRATION. NBI record format. Dicionário dos arquivos históricos. www.fhwa.dot.gov/bridge/nbi/format.cfm.

[7] GNEITING, T.; RAFTERY, A. E. Strictly proper scoring rules, prediction, and estimation. Journal of the American Statistical Association, v. 102, p. 359–378, 2007. DOI 10.1198/016214506000001437.

[8] DNIT. Norma DNIT 010/2024–PRO. Inspeções em pontes, viadutos e passarelas rodoviárias. Brasília, 2024.
