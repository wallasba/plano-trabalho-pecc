Universidade de Brasília

Programa de Pós-Graduação em Estruturas e Construção Civil

Plano de Trabalho e Pesquisa • Doutorado

# Transferência de aprendizado para prever a condição da superestrutura de pontes e viadutos rodoviários com poucos registros locais de inspeção

Wallas Borges Araújo

Área de concentração em Estruturas

Linha de pesquisa em Métodos Numéricos e Computacionais Aplicados à Engenharia (Estruturas)

Brasília, novembro de 2026

<!-- página -->

## 1. Introdução

Uma equipe dispõe de recursos para iniciar estudos de intervenção em apenas parte das pontes e viadutos sob sua responsabilidade. Entre duas pontes com a mesma nota de condição da superestrutura, uma manteve a nota nas últimas inspeções e a outra chegou a ela após quedas sucessivas. Se os demais critérios técnicos lhes atribuem prioridade equivalente, o histórico acrescenta informação para escolher qual delas encaminhar para estudo? A pesquisa examinará essa questão em pontes e viadutos rodoviários de concreto armado, concreto protendido, aço ou construção mista [15].

Históricos de outros inventários oferecem exemplos adicionais. Entretanto, o desempenho obtido na origem pode se perder no destino quando mudam as tipologias predominantes, as práticas de manutenção ou a atribuição das notas. A pesquisa irá prever a distribuição da nota ordinal de condição da superestrutura na próxima inspeção rotineira registrada no National Bridge Inventory (NBI). A nota, registrada no item 59, representa a condição física dos elementos estruturais considerados pelo procedimento de inspeção [1]. A avaliação da capacidade resistente exigiria outras observações e outro modelo.

**Perguntas de pesquisa.** Quando há poucos históricos locais, que peso atribuir às previsões de outros estados para estimar a próxima nota da superestrutura? Para um número fixo de estudos, acrescentar essa previsão aos critérios técnicos aumenta a seleção de obras que posteriormente recebem recomendação técnica de estudo de intervenção?

**Hipótese.** Com poucas inspeções locais, uma vantagem aparente dos dados externos pode decorrer da composição da amostra. A hipótese é que considerar a incerteza dessa vantagem ao escolher o peso externo reduzirá a perda média nos estados em que a transferência pioraria a previsão. A perda será calculada em todos os destinos, atribuindo valor zero quando o método igualar ou superar o modelo local. A comparação será com a mesma regra sem penalidade, para cada quantidade de dados locais.

## 2. Justificativa

A formação de uma carteira de estudos antecede a decisão de financiar intervenções. Nesta etapa, o gestor identifica obras que justificam diagnóstico e comparação de alternativas. No âmbito do PROARTE, informações das inspeções subsidiam o planejamento das intervenções [15, 16]. Uma ponte em condição grave pode exigir providências mesmo que sua nota permaneça estável. Para obras com prioridade técnica equivalente, interessa saber quanto a trajetória prevista acrescenta à escolha. A decisão posterior de investimento exige alternativas de engenharia, estimativas de custos e benefícios e disponibilidade orçamentária. Na linha de métodos numéricos e computacionais do PECC, a tese investigará a incerteza da evolução prevista e os limites do uso de dados externos por material e tipologia.

## 3. Objetivos

**Objetivo geral.** Desenvolver e avaliar um método de transferência adaptativa de aprendizado para prever a nota de condição da superestrutura na próxima inspeção rotineira e investigar em que condições essa previsão pode apoiar a seleção de pontes e viadutos para estudos de intervenção.

**Objetivos específicos**

1. Reconstruir históricos comparáveis por estrutura, distinguindo novas inspeções, republicações e alterações cadastrais.
2. Estimar o peso da previsão de origem por uma regra que considere a incerteza da diferença de erro em relação ao modelo local.
3. Quantificar o benefício e a perda por transferência sob diferentes quantidades de dados locais, materiais e tipologias.
4. Elaborar um protocolo de seleção de obras para estudos de intervenção e, havendo recomendações técnicas independentes, medir o ganho da previsão em relação aos critérios técnicos disponíveis ao gestor. Especificar os requisitos para aplicação no Brasil.

## 4. Revisão da literatura

Behrooz e Ilbeigi [2] produziram previsões probabilísticas ordinais para o ano seguinte com registros do NBI de Nova Jersey, Nova York e Connecticut. O caráter ordinal permite distinguir uma previsão próxima da nota observada de outra que atribui alta probabilidade a uma condição muito superior à registrada.

Chen, Yuan e Lin [3] compartilharam parâmetros entre nove agências canadenses por transferência bayesiana hierárquica e modelaram a evolução do índice de condição da ponte (*Bridge Condition Index*, BCI). O estudo considera diferenças entre agências e a escassez de registros locais. O problema aqui é estimar quanto peso dar à previsão externa para a nota ordinal da superestrutura na próxima inspeção registrada.

Yao e colaboradores [4, 5] estimam pesos de combinação de distribuições pelo desempenho fora da amostra e permitem, na extensão hierárquica, que esses pesos variem com os dados. Gu, Lee e Duan [6] combinam previsões locais e de origem com base no desempenho em dados de validação do destino. Kim [7] avalia regras de combinação que incluem o modelo exclusivamente local entre os candidatos. Como o uso de dados externos pode aumentar o erro no destino, a comparação com um modelo exclusivamente local permite medir a transferência negativa [8].

A contribuição a testar é se penalizar a incerteza da diferença de erro em relação ao modelo local, estimada por reamostragem de estruturas, reduz as perdas em estados e inspeções reservados. A comparação direta será com a mesma combinação de previsões sem penalidade.

No Brasil, Souza e colaboradores [9] propuseram modelos de transição com matrizes de Markov a partir de inspeções de 885 pontes e dados simulados. Posteriormente, aplicaram um índice de deterioração à priorização de intervenções em 2.134 pontes [10]. Esta tese examinará uma questão complementar. Quando o histórico local é curto, em que condições as observações de outras regiões melhoram a previsão da próxima nota e quanto essa informação acrescenta à seleção de candidatas a estudos?

## 5. Metodologia

### 5.1 População, dados e evidência preliminar

O estudo será longitudinal, retrospectivo e integralmente remoto. A fonte principal será o NBI, mantido pela Federal Highway Administration (FHWA). Os arquivos históricos no formato ASCII seguem o guia de codificação até a edição de 2025 [1, 11, 12]. O estado será a unidade de agrupamento. Serão elegíveis estruturas que conduzam tráfego rodoviário (item 42A, códigos 1, 4, 5, 6, 7 ou 8), com vão principal de concreto ou aço (43A, códigos 1 a 6). A identificação de estruturas mistas exigirá documentação complementar. O item 43B excluirá túneis e bueiros (18 e 19). O serviço sob a obra (42B) contextualizará a travessia. Pontes e viadutos serão analisados em conjunto e distinguidos apenas quando a documentação permitir. Cada estrutura deverá ter nota numérica no item 59 em pelo menos duas inspeções com mês e ano distintos.

A unidade de previsão será o par de inspeções rotineiras consecutivas registradas para a mesma estrutura. A chave longitudinal combinará estado e número da estrutura (itens 1 e 8). O item 90 informa o mês e o ano da última inspeção rotineira, o item 91 registra o intervalo programado em meses e o item 59 contém a nota da superestrutura [1, 12]. Os identificadores serão preservados como texto. Para cada previsão, será usada a edição disponível na data de corte. O modelo receberá a última nota conhecida, o histórico anterior, o intervalo programado, o material, a tipologia, a idade e o vão, quando disponíveis. O mês e o ano da próxima inspeção registrada identificarão o desfecho e permitirão examinar diferenças de horizonte.

**Piloto de viabilidade.** A leitura dos quatro arquivos de Delaware, de 2022 a 2025, encontrou respectivamente 872, 874, 872 e 874 registros. Considerando nota numérica e mês válido, 1.228 ocorrências repetiram uma combinação de estrutura e data já observada. Em 40 dessas ocorrências, a nota diferiu da versão anterior. Adotando a última ocorrência disponível para cada chave e data, 555 estruturas forneceram 784 pares de datas sucessivas. Houve 76 quedas, 77 aumentos e 631 permanências de nota. As contagens antecedem os filtros de tráfego, material e tipologia. O piloto ampliado repetirá a contagem de estruturas, pares e quedas após cada filtro. A origem das revisões e a cobertura em outros estados ainda exigem auditoria [11, 12].

Na análise principal serão excluídos pares com conflito de nota na mesma data ou indício de mudança de identidade da obra. A análise de sensibilidade repetirá a estimação com as revisões documentadas. Reconstruções identificáveis serão marcadas e os resultados examinados com e sem os intervalos correspondentes. Uma melhora de nota pode refletir reparo, variação de avaliação ou revisão de cadastro. A interpretação ficará limitada às mudanças registradas. Serão descritas também as estruturas sem retorno observado, pois a frequência de inspeção pode estar associada à condição.

### 5.2 Modelagem e contribuição proposta

Em cada estado de destino, um modelo ordinal de transição fornecerá as probabilidades das notas futuras, condicionadas à última nota e aos atributos disponíveis. O modelo local será regularizado para estabilizar as estimativas em amostras pequenas. Um modelo da mesma família será ajustado com dados dos estados de origem. A transferência adaptativa combinará as distribuições preditivas dos dois modelos por uma média ponderada, com peso externo entre zero e um ajustado pelo desempenho em inspeções anteriores do destino.

A regra candidata usará previsões retrospectivas produzidas em ordem temporal no conjunto de desenvolvimento. Para cada peso candidato, será calculada nas mesmas inspeções a diferença entre o escore probabilístico ordinal (*Ranked Probability Score*, RPS) da combinação e o do modelo local. A regra escolherá o peso que minimize a diferença média acrescida de uma penalidade proporcional ao erro padrão dessa diferença. O erro padrão será estimado reamostrando estruturas inteiras, com todas as suas inspeções elegíveis. O peso externo zero reproduz a previsão exclusivamente local. A intensidade da penalidade será escolhida em estados de desenvolvimento tratados alternadamente como destinos e fixada antes da avaliação externa.

Para isolar o efeito da penalidade, a combinação sem penalidade usará as mesmas previsões, inspeções e opções de peso, incluindo o peso zero. As demais referências serão a persistência da última nota, o modelo exclusivamente local, o ajuste conjunto sem distinção entre estados, o modelo aplicado diretamente da origem, o compartilhamento hierárquico de parâmetros e a combinação hierárquica de previsões [3–7]. Cada estratégia terá acesso ao mesmo conjunto local. A ausência completa de históricos será avaliada separadamente pela aplicação direta do modelo de origem, pois a calibração do peso exige desfechos locais observados.

### 5.3 Experimento e medida principal

Cada rodada reservará um estado como destino. A escolha da intensidade da penalidade usará exclusivamente os demais estados e registros anteriores ao corte temporal. No destino, o período inicial servirá ao ajuste do modelo local, o seguinte à calibração do peso externo e o último ao teste. A escassez será simulada por subamostras de estruturas com seus históricos elegíveis. As contagens após os filtros no piloto ampliado orientarão os tamanhos das amostras, fixados antes do teste. Cada previsão usará os atributos disponíveis na data de corte. Uma análise adicional reservará estruturas inteiras para avaliar o desempenho em obras novas.

O RPS será a medida principal. Para cada limiar entre categorias adjacentes, calcula-se a diferença entre a probabilidade prevista de uma nota até aquele limiar e o indicador de que a nota observada é igual ou inferior a ele. O RPS normalizado é a média dos quadrados dessas diferenças. Quanto menor o valor, melhor a previsão [13, 14]. Os escores serão resumidos primeiro por estrutura e depois por estado. Cada estado terá o mesmo peso no resumo principal.

Para cada estado e tamanho da amostra local, a perda será o excesso do RPS médio do método sobre o do modelo local nas mesmas inspeções, com valor zero quando o método igualar ou superar a referência. A hipótese prevê que a média dessas perdas entre estados seja menor com a penalidade. Para cada tamanho amostral serão apresentados a diferença pareada entre as duas regras e sua incerteza, o RPS médio total, a frequência de transferência negativa e os ganhos obtidos nos estados em que a transferência reduziu o erro. Os pesos externos escolhidos indicarão com que frequência cada regra recorreu apenas ao modelo local. A calibração será avaliada por faixa de probabilidade prevista de queda. Os resultados por material, tipologia e nota inicial informarão o número de estruturas e quedas. Grupos com poucos eventos terão interpretação descritiva.

### 5.4 Seleção de obras para estudos de intervenção

Em cada data de corte, serão reproduzidos os critérios técnicos documentados pelo gestor e disponíveis naquela data. Obras já encaminhadas em caráter de urgência seguirão a indicação técnica e serão contabilizadas separadamente. Para as vagas restantes, duas listas selecionarão o mesmo número de candidatas entre as mesmas obras elegíveis. A primeira seguirá a ordem técnica de referência. A segunda manterá as classes de prioridade e, dentro de cada classe, dará precedência à maior probabilidade prevista de queda da nota. Será preservado o desempate usual na lista de referência ou, se não houver regra registrada, uma ordem fixa de identificadores. Capacidade, classes, desempates e janela de acompanhamento serão fixados antes do teste. A comparação identificará as obras cuja inclusão mudou na última classe com vagas disponíveis.

O desfecho aplicado será uma recomendação técnica posterior e datada de estudar uma intervenção na superestrutura, emitida independentemente das previsões. Serão distinguidos os casos com indicação, os avaliados sem indicação e aqueles sem avaliação conclusiva na janela. Para cada lista, serão informados os números de indicações entre as selecionadas e entre as demais, além da cobertura da avaliação nos dois grupos. A diferença de indicações captadas para a mesma capacidade estimará o ganho observado. Se a documentação se concentrar nas obras já priorizadas, serão apresentados limites para essa diferença, atribuindo os desfechos desconhecidos das obras que mudaram de lista ora a favor, ora contra a seleção preditiva. A queda de nota será avaliada separadamente como desfecho da previsão.

A aplicação a outro inventário exigirá um identificador estável por obra, datas que distingam inspeções de atualizações cadastrais, identificação do componente e notas sucessivas com critérios documentados. O protocolo registrará a direção da escala, o que caracteriza piora e a cobertura dos atributos usados pelo modelo. No caso brasileiro, os anexos B a D da DNIT 010/2024–PRO orientarão a comparação das notas por elemento (1 a 5) com a nota da superestrutura no NBI (0 a 9) [1, 15]. Quando vigas e lajes receberem notas individuais, será preciso justificar como elas representam a condição do conjunto. A correspondência proposta deverá ter respaldo nos manuais ou em avaliações das mesmas obras pelos dois procedimentos. Com documentação apenas, o produto será um diagnóstico de compatibilidade. Com cadastro disponível, será examinada a cobertura dos atributos. Havendo correspondência fundamentada e históricos sucessivos autorizados, o método adaptado será comparado ao modelo local em inspeções posteriores reservadas, na escala do destino. O experimento principal usará dados públicos do NBI.

A DNIT 010/2024–PRO também abrange passarelas. Nos Estados Unidos, as normas federais de inspeção de pontes excluem travessias exclusivamente de pedestres [15, 17]. Uma extensão exploratória para passarelas terá análise separada, condicionada à licença de uso, a históricos comparáveis e a eventos suficientes para estimar o desempenho. Túneis e contenções, contemplados pelo PROARTE [16], ficam para pesquisas futuras com inventários, componentes e desfechos próprios.

### 5.5 Cronograma e produtos

**Ano 1.** Revisar os antecedentes, auditar os dados de múltiplos estados e formar o painel de inspeções. Verificar acesso, datas, independência e cobertura das recomendações técnicas, inclusive para obras historicamente não selecionadas. Registrar os critérios de elegibilidade, partições e métricas e elaborar o dicionário de dados.

**Ano 2.** Ajuste dos modelos de referência, implementação da regra adaptativa em Python e experimentos de desenvolvimento. Produto previsto: implementação documentada com cálculo dos pesos e dos escores por estrutura.

**Ano 3.** Avaliação em estados e períodos reservados, curvas de desempenho por disponibilidade local, comparação dos componentes e estudo das situações de transferência negativa. Produto previsto: artigo sobre o método e seus limites de aplicação.

**Ano 4.** Concluir o protocolo de seleção e documentar sua aplicação ao contexto brasileiro. Havendo critérios de prioridade e avaliações posteriores comparáveis, testar as duas listas em períodos reservados. Se houver apenas históricos de notas, entregar a avaliação preditiva e o protocolo para validação futura com o DNIT. Consolidar os resultados na tese.

## 6. Referências bibliográficas

[1] FEDERAL HIGHWAY ADMINISTRATION. *Recording and Coding Guide for the Structure Inventory and Appraisal of the Nation’s Bridges*. Washington, DC, 1995. FHWA-PD-96-001. www.fhwa.dot.gov/bridge/mtguide.pdf.

[2] BEHROOZ, H.; ILBEIGI, M. An ordinal autoregressive deep learning model for probabilistic prediction of bridge deterioration condition levels. *Structure and Infrastructure Engineering*, 2025. DOI 10.1080/15732479.2025.2571872.

[3] CHEN, W.; YUAN, A. X.-X.; LIN, P. Cross-jurisdictional collaborative deterioration modeling via hierarchical Bayesian transfer learning. *Computer-Aided Civil and Infrastructure Engineering*, v. 40, p. 6456–6474, 2025. DOI 10.1111/mice.70159.

[4] YAO, Y.; VEHTARI, A.; SIMPSON, D.; GELMAN, A. Using stacking to average Bayesian predictive distributions (with discussion). *Bayesian Analysis*, v. 13, n. 3, p. 917–1007, 2018. DOI 10.1214/17-BA1091.

[5] YAO, Y.; PIRŠ, G.; VEHTARI, A.; GELMAN, A. Bayesian hierarchical stacking: some models are (somewhere) useful. *Bayesian Analysis*, v. 17, n. 4, p. 1043–1071, 2022. DOI 10.1214/21-BA1287.

[6] GU, T.; LEE, P. H.; DUAN, R. COMMUTE: Communication-efficient transfer learning for multi-site risk prediction. *Journal of Biomedical Informatics*, v. 137, art. 104243, 2023. DOI 10.1016/j.jbi.2022.104243.

[7] KIM, Y. Measuring negative transfer in multi-source learning: weight normalization, target-label budgets, and validation-based mixing. *Neurocomputing*, art. 135609, 2027. DOI 10.1016/j.neucom.2026.135609.

[8] WANG, Z.; DAI, Z.; PÓCZOS, B.; CARBONELL, J. Characterizing and avoiding negative transfer. In: *IEEE/CVF Conference on Computer Vision and Pattern Recognition*, 2019. p. 11293–11302. DOI 10.1109/CVPR.2019.01155.

[9] SOUZA, C. A. F. de et al. Probabilistic bridge deterioration prediction models based on Markov matrices using real and simulated data from deterministic models. *Revista IBRACON de Estruturas e Materiais*, v. 17, n. 1, 2024. DOI 10.1590/S1983-41952024000100015.

[10] SOUZA, C. A. F. de et al. Bridge deterioration index for prioritizing interventions and planning inspections in Brazil. *Revista IBRACON de Estruturas e Materiais*, v. 19, n. 3, e19123, 2026. DOI 10.1590/S1983-41952026000100023.

[11] FEDERAL HIGHWAY ADMINISTRATION. *National Bridge Inventory: download NBI ASCII files*. Arquivos históricos, incluindo as edições de Delaware de 2022 a 2025. www.fhwa.dot.gov/bridge/nbi/ascii.cfm.

[12] FEDERAL HIGHWAY ADMINISTRATION. *NBI record format*. Leiaute dos arquivos históricos. www.fhwa.dot.gov/bridge/nbi/format.cfm.

[13] EPSTEIN, E. S. A scoring system for probability forecasts of ranked categories. *Journal of Applied Meteorology*, v. 8, n. 6, p. 985–987, 1969. journals.ametsoc.org/view/journals/apme/8/6/1520-0450_1969_008_0985_assfpf_2_0_co_2.xml.

[14] GNEITING, T.; RAFTERY, A. E. Strictly proper scoring rules, prediction, and estimation. *Journal of the American Statistical Association*, v. 102, n. 477, p. 359–378, 2007. DOI 10.1198/016214506000001437.

[15] DEPARTAMENTO NACIONAL DE INFRAESTRUTURA DE TRANSPORTES. *DNIT 010/2024 – PRO: Inspeções em pontes e viadutos – Procedimento*. Brasília, DF, 2024. 22 p.

[16] DEPARTAMENTO NACIONAL DE INFRAESTRUTURA DE TRANSPORTES. *Instrução Normativa nº 2/DNIT SEDE, de 5 de março de 2026*. PROARTE. Boletim Administrativo nº 045, 9 mar. 2026. Retificação no nº 094, 21 maio 2026.

[17] FEDERAL HIGHWAY ADMINISTRATION. *National Bridge Inspection Standards: Questions and Answers, 650.303 Applicability*. Questão Q303-1, 2023. www.fhwa.dot.gov/bridge/nbis2022/qanda/03.cfm.
