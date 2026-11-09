\begin{titlepage}
\centering
\vspace*{4cm}
{\Large Wallas Borges Araújo\par}
\vspace{2cm}
{\LARGE Plano de Trabalho e Pesquisa\par}
\vspace{1cm}
{\large Confiabilidade de métodos de detecção de mudanças estruturais em pontes sob indisponibilidade de sensores\par}
\vspace{2cm}
{\large Área de concentração: Estruturas\par}
\vspace{0.5cm}
{\large Linha de pesquisa: Desenvolvimento de Métodos Numéricos e Analíticos na Engenharia\par}
\vspace{0.5cm}
{\normalsize (linha proposta; confirmar a aderência com a orientação antes da submissão)\par}
\vfill
{\large Novembro de 2026\par}
\end{titlepage}
\newpage

## 1. Introdução

O monitoramento da saúde estrutural (Structural Health Monitoring — SHM) emprega medições de sensores para acompanhar o comportamento de estruturas e identificar mudanças que possam requerer investigação. Em pontes monitoradas, alterações em aceleração, deformação e outras respostas podem decorrer de dano, condições ambientais e operacionais, mudanças de instrumentação ou falhas de medição. Por isso, uma saída classificatória isolada não basta: é necessário saber em que condições o método erra, quão incerta é sua decisão e se ele continua operando quando parte dos sensores deixa de fornecer dados.

Esta pesquisa delimita o problema à **confiabilidade da detecção de mudanças estruturais sob indisponibilidade controlada de canais de medição**, com uma regra de abstenção quando a evidência for insuficiente. A base principal candidata é o Hell Bridge Test Arena (HBTA), um benchmark experimental aberto de ponte de aço em escala real com estado de referência e estados de dano imposto. A base externa candidata é Vänersborg, na Suécia: 64 arquivos CSV de eventos de abertura, com dados de aceleração, deformação, inclinação e meteorologia a 200 Hz e uma fratura verificada. O artigo dessa base informa que um sistema comercial em nuvem já emitiu um alarme para a anomalia (Leander et al., 2023). Vänersborg será tratada como estudo de caso externo, não como amostra suficiente para estimar generalização entre pontes.

**Pergunta de pesquisa:** sob quais cenários de indisponibilidade de canais de sensores os métodos de detecção de mudanças estruturais deixam de sustentar decisões confiáveis em um benchmark experimental de ponte, e a abstenção baseada em incerteza reduz o risco das decisões emitidas a um custo aceitável de cobertura?

**Hipótese de trabalho:** a retirada estruturada de canais pode degradar de forma desigual os indicadores de detecção; uma regra seletiva calibrada sem acesso ao teste poderá reduzir o risco entre as decisões emitidas, explicitando a perda de cobertura. A hipótese será rejeitada se esse trade-off não se reproduzir em partições por ensaio/estado, depender de cenários artificiais sem interpretação física ou não superar regras simples de rejeição. A investigação não pressupõe que a quantificação de incerteza ou a avaliação de sensores sejam novas: ambas têm antecedentes diretos em SHM e no próprio HBTA.

O estudo será quantitativo e computacional, usando exclusivamente dados digitais existentes e acessados remotamente. Não prevê visita a campo, instalação de sensores, coleta presencial ou novos ensaios físicos. Ruído e canais removidos artificialmente serão testes de estresse e não serão apresentados como falhas reais observadas.

## 2. Justificativa

Uma limitação prática de sistemas de monitoramento é a possibilidade de perda, falha ou indisponibilidade parcial dos sensores. Embora a detecção de mudanças e o efeito de condições ambientais em SHM tenham literatura consolidada, não se deve inferir robustez operacional a partir de resultados obtidos com todos os canais disponíveis, nem de partições que distribuam janelas correlacionadas entre treino e teste. Revisões de métodos de SHM e estudos de dados de pontes documentam a diversidade de estratégias e a dificuldade de generalizar conclusões entre estruturas (Deng et al., 2023; Eltouny et al., 2023; Keshmiry et al., 2023).

A contribuição potencial será uma avaliação reproduzível e centrada em grupos experimentais que relacione cenários de disponibilidade de sensores, calibração, risco-cobertura e limites de decisão seletiva. Isso precisa ser diferenciado dos estudos existentes sobre configuração de sensores, propagação de incerteza e stress testing de dados. O trabalho de Hu et al. (2026), por exemplo, já aplica stress testing group-aware a Vänersborg e Z24; del Pozo et al. (2025) já estudam propagação explícita de incerteza para detecção de dano com dados experimentais de ponte; e del Pozo et al. (2024) examinam sensibilidade a configurações de sensores no HBTA. Portanto, não se reivindica originalidade pelo tema amplo nem por introduzir remoção de sensores ou métricas de incerteza. A originalidade dependerá de demonstrar, após auditoria dos artigos completos, uma pergunta e análise não respondidas por esses estudos. A tese não tratará anomalia estatística como diagnóstico de segurança, localização ou severidade do dano.

A HBTA é a base principal candidata porque reúne estados de referência e danos impostos em um experimento de ponte em escala real, sendo mais apropriada que uma única fratura observacional para comparações entre grupos de ensaios. Contudo, já há estudos de detecção de dano, configurações de sensores e incerteza usando esse benchmark; o acesso aberto ao conjunto não demonstra que a contribuição proposta seja original. Vänersborg oferece um caso complementar de dano real verificado e licença CC BY 4.0, mas apenas uma ponte e um episódio de fratura descrito, além de confundimento potencial entre dano, tempo e operação; por isso, servirá para uma análise externa limitada, sem inferência estatística de generalização. Se a auditoria do HBTA não confirmar grupos independentes suficientes para a pergunta, ou se a revisão mostrar sobreposição integral com resultados publicados, o recorte deverá ser reformulado antes da modelagem.

A aderência proposta é à área de Estruturas, pelo objeto de estudo e pela interpretação de mudanças em pontes, com componente de métodos computacionais e estatísticos. A linha institucional que melhor corresponde ao método é “Desenvolvimento de Métodos Numéricos e Analíticos na Engenharia”, que inclui aplicações de inteligência artificial e aprendizado de máquina; a aderência concreta e a disponibilidade de orientação/coorientação ainda devem ser confirmadas com o PECC. Não se alegará validação para pontes brasileiras sem dados nacionais digitais autorizados e apropriados; não haverá coleta presencial como contingência.

## 3. Objetivos

### Objetivo geral

Desenvolver e avaliar um protocolo reproduzível para quantificar a confiabilidade de métodos de detecção de mudanças estruturais em dados de pontes sob indisponibilidade controlada de canais de sensores.

### Objetivos específicos

1. Auditar os arquivos, documentação, licença, unidades experimentais, metadados, canais e rótulos do HBTA e do caso externo Vänersborg.
2. Definir uma tarefa de detecção compatível com os estados e grupos experimentais efetivamente documentados no HBTA.
3. Comparar métodos e baselines sob disponibilidade completa e cenários controlados de remoção de canais, com partições por ensaio/estado que evitem vazamento.
4. Avaliar discriminação, falsos alarmes e calibração por cenário, respeitando o número de unidades experimentais independentes.
5. Investigar uma regra de abstenção e mensurar o compromisso entre risco seletivo e cobertura em comparação com regras simples.
6. Avaliar em Vänersborg apenas a sensibilidade do caso da fratura verificada, explicitando que um caso não constitui validação externa populacional.
7. Confrontar a contribuição com estudos publicados sobre HBTA, incerteza e qualidade de dados antes de reivindicar originalidade.

## 4. Revisão da Literatura

A revisão será focalizada em quatro eixos: (i) SHM de pontes e detecção de mudanças/danos a partir de dados dinâmicos; (ii) efeitos ambientais e operacionais e limites de identificação em séries observacionais; (iii) dados ausentes, falhas de sensores e robustez a mudanças na configuração de medição; e (iv) calibração, quantificação de incerteza e classificação seletiva em aplicações com risco de falso alarme.

Revisões recentes discutem SHM de pontes, efeitos ambientais/operacionais e aprendizado não supervisionado (Deng et al., 2023; Eltouny et al., 2023; Keshmiry et al., 2023). A literatura já inclui detecção de dano a partir dos dados experimentais do HBTA (Svendsen et al., 2022), abordagens híbridas sob efeitos ambientais simulados (Svendsen et al., 2023), sensibilidade a configurações de sensores (del Pozo et al., 2024), e propagação explícita de incerteza em indicadores de dano (del Pozo et al., 2025). No domínio de qualidade de dados, Hu et al. (2026) aplicam avaliação group-aware a 64 eventos de Vänersborg e cenários processados de Z24. Dados ausentes e falhas de sensores também têm métodos publicados (Deng et al., 2023; Lydakis et al., 2024), assim como calibração e decisão seletiva (Guo et al., 2017; Geifman; El-Yaniv, 2017). A proposta, portanto, não apresenta esses tópicos isolados como lacuna; a revisão integral deverá verificar se a combinação específica de perdas estruturadas de canais, decisões seletivas e separação experimental no HBTA ainda não foi respondida. O Z24 só será candidato a análise complementar mediante autorização de acesso e licença de uso não comercial.

## 5. Metodologia

### 5.1 Auditoria e seleção de dados

A pesquisa começará com auditoria dos metadados, artigos e arquivos disponíveis, registrando versão, licença, formatos, canais, frequências de amostragem, estados, grupos experimentais, rótulos, documentação e estudos associados. O registro HBTA disponibiliza gratuitamente, sob CC BY 4.0, um arquivo HDF5 de 2,5 GB a 100 Hz, arquivos auxiliares de processamento, desenhos e layout de sensores. Sua documentação descreve medições de resposta e carga para condições estruturais entre referência sem dano e estados com dano imposto. A auditoria direta deverá determinar a quantidade de ensaios independentes por estado, os identificadores de ensaio/configuração, as variáveis ambientais e operacionais realmente medidas, canais inutilizáveis, estrutura dos arquivos e replicabilidade do pré-processamento. O conjunto Vänersborg (ZIP de 551,7 MB, CC BY 4.0) é documentado como 64 CSVs de 200 Hz, com timestamps UTC, 16 strain gauges, cinco acelerômetros, um inclinômetro e variáveis meteorológicas; valores de canais sem sensor conectado devem ser excluídos e o delimitador decimal por vírgula deve ser tratado. O evento de propagação da trinca é identificado no artigo como `2023_03_09T23_45_25.csv`. A auditoria de Vänersborg confirmará a possibilidade de reproduzir uma análise do caso, sem tratá-lo como amostra independente de danos.

O HBTA é ensaio experimental de uma ponte de aço com danos impostos, não monitoramento de longo prazo em serviço. Será a base quantitativa principal, se a auditoria confirmar replicação e agrupamento adequados. O Z24 poderá ser solicitado como alternativa/sensibilidade; não é requisito para a viabilidade central e não será considerado aberto para download irrestrito.

### 5.2 Definição da tarefa e controles contra confundimento

As unidades independentes serão os ensaios ou grupos experimentais definidos pela documentação do HBTA, não janelas ou amostras derivadas. A tarefa será estabelecida após a auditoria dos rótulos e condições: detecção de dano ou mudança entre estados de referência e dano imposto, sem misturar segmentos do mesmo ensaio entre treino, calibração e teste. Se não houver número suficiente de grupos independentes por estado, a análise será descritiva ou reformulada; não se apresentará precisão em milhares de janelas correlacionadas como evidência de generalização. Em Vänersborg, o arquivo do evento de propagação da trinca será mantido separado, analisado como caso singular e sem estimar uma taxa generalizável de detecção.

No HBTA, os danos são impostos em ensaio, mas os resultados não se transferem automaticamente a pontes em serviço. Serão separados, quando possível, efeitos de configuração experimental, condição estrutural e condição de excitação, usando controles que explorem informação auxiliar sem resposta estrutural. Em Vänersborg, o estado de dano pode estar confundido com tempo, operação ou meteorologia; por isso, resultados desse caso serão descritos como análise exploratória e não como validação diagnóstica de segurança.

### 5.3 Modelos, cenários e protocolo de avaliação

Serão comparados baselines estatísticos de referência/anomalia e métodos compatíveis com a tarefa escolhida, incluindo, se pertinente, os algoritmos reproduzíveis descritos nos estudos de referência do HBTA. O desenho será confrontado com trabalhos existentes de detecção, decisão, configuração de sensores e incerteza; qualquer método novo dependerá de uma lacuna documentada. Deep learning não será presumido: só será incluído se o número de ensaios independentes justificar sua avaliação sem vazamento.

O cenário de referência utilizará os canais elegíveis disponíveis. Cenários de estresse removerão canais individuais ou subconjuntos por padrões previamente especificados, com níveis de disponibilidade documentados. Não serão apresentados como falhas reais. Se faltas reais estiverem documentadas, serão analisadas separadamente e sem misturá-las com remoção artificial.

As partições respeitarão o evento e, quando viável, a ordem temporal. A calibração e escolha de limiares utilizarão apenas o conjunto de referência permitido pelo protocolo; o teste final não será reutilizado para ajustar parâmetros. Serão relatados, conforme a tarefa: sensibilidade, especificidade, precisão, revocação, F1, AUROC/AUPRC, taxa de falsos alarmes por evento e métricas de calibração (por exemplo, Brier score). A decisão seletiva será avaliada por curvas de risco versus cobertura, incluindo a proporção de eventos em que o método se abstém. As métricas e uma métrica primária serão pré-especificadas após a auditoria.

Resultados serão apresentados por cenário e não apenas como média global. Reamostragem e intervalos de confiança respeitarão eventos como unidades independentes; devido ao pequeno número de unidades e a um único episódio de dano, qualquer intervalo será interpretado com cautela, e não se fará inferência sobre uma população de pontes a partir de janelas correlacionadas. Hiperparâmetros, limiares, sementes, pré-processamento e código serão documentados, observadas as licenças.

### 5.4 Validação externa, viabilidade e riscos

Vänersborg será usado como análise externa de um episódio de dano real verificado, somente para verificar se os achados qualitativos do benchmark experimental são compatíveis com um caso em serviço. Não serão combinadas amostras nem estimada transferência entre domínios a partir de um único caso. Z24 e dados NTNU poderão compor revisão e contextualização, respeitadas suas condições de acesso.

O processamento inicial será feito em Python e dimensionado por piloto de leitura, memória e armazenamento. O HDF5 do HBTA tem aproximadamente 2,5 GB; o ZIP de Vänersborg, 551,7 MB. CPU deve bastar para inventário e baselines; GPU não é requisito presumido. Riscos principais: poucas unidades independentes, sobreposição com publicações recentes, confundimento de configuração experimental, insuficiência de rótulos para avaliar calibração seletiva e diferença entre ensaio controlado e ponte em serviço. Se a auditoria ou a revisão revelar que o HBTA não sustenta uma pergunta original, a contingência será reformular o tema antes dos experimentos, não ampliar artificialmente a amostra por janelas correlacionadas.

### 5.5 Etapas e cronograma indicativo

1. **Ano 1:** revisão focada, confirmação de orientação/linha, auditoria dos arquivos, definição da tarefa e pré-registro do protocolo analítico.
2. **Ano 2:** implementação dos baselines, análise exploratória, construção das partições por evento e piloto de disponibilidade de sensores.
3. **Ano 3:** avaliação comparativa, calibração/abstenção, análise de incerteza e testes de robustez, com documentação reproduzível.
4. **Ano 4:** validação externa condicional, síntese, publicação, redação e defesa da tese.

O cronograma é indicativo e deve ser compatibilizado com o prazo regulamentar do doutorado e com o plano acordado com a orientação.

## 6. Referências Bibliográficas

1. DENG, Z.; HUANG, M.; WAN, N.; ZHANG, J. The Current Development of Structural Health Monitoring for Bridges: A Review. *Buildings*, v. 13, n. 6, 1360, 2023. DOI: [10.3390/buildings13061360](https://doi.org/10.3390/buildings13061360).
2. ELTOUNY, K.; GOMAA, M.; LIANG, X. Unsupervised Learning Methods for Data-Driven Vibration-Based Structural Health Monitoring: A Review. *Sensors*, v. 23, n. 6, 3290, 2023. DOI: [10.3390/s23063290](https://doi.org/10.3390/s23063290).
3. KESHMIRY, A.; HASSANI, S.; MOUSAVI, M.; DACKERMAN, U. Effects of Environmental and Operational Conditions on Structural Health Monitoring and Non-Destructive Testing: A Systematic Review. *Buildings*, v. 13, n. 4, 918, 2023. DOI: [10.3390/buildings13040918](https://doi.org/10.3390/buildings13040918).
4. LEANDER, J.; NYMAN, J.; KAROUMI, R.; ROSENGREN, P.; JOHANSSON, G. Dataset for damage detection retrieved from a monitored bridge pre and post verified damage. *Data in Brief*, v. 51, 109729, 2023. DOI: [10.1016/j.dib.2023.109729](https://doi.org/10.1016/j.dib.2023.109729). Dados: [Zenodo 8300495](https://doi.org/10.5281/zenodo.8300495), licença CC BY 4.0.
5. PEETERS, B.; DE ROECK, G. One-year monitoring of the Z24-bridge: environmental effects versus damage events. *Earthquake Engineering & Structural Dynamics*, v. 30, n. 2, p. 149–171, 2001. DOI: [10.1002/1096-9845(200102)30:2<149::AID-EQE1>3.0.CO;2-Z](https://doi.org/10.1002/1096-9845(200102)30:2%3C149::AID-EQE1%3E3.0.CO;2-Z).
6. SVENDSEN, B. T.; FRØSETH, G. T.; ØISETH, O.; RØNNQUIST, A. A data set from an extensive experimental benchmark study of the Hell Bridge Test Arena subject to imposed damage. *Journal of Structural Engineering*, v. 151, n. 12, 2025. DOI: [10.1061/JSENDH.STENG-14818](https://doi.org/10.1061/JSENDH.STENG-14818). Dados: [Zenodo 14632942](https://doi.org/10.5281/zenodo.14632942), licença CC BY 4.0.
7. SVENDSEN, B. T.; FRØSETH, G. T.; ØISETH, O.; RØNNQUIST, A. A data-based structural health monitoring approach for damage detection in steel bridges using experimental data. *Journal of Civil Structural Health Monitoring*, v. 12, p. 101–115, 2022. DOI: [10.1007/s13349-021-00530-8](https://doi.org/10.1007/s13349-021-00530-8).
8. DEL POZO, G. A.; SVENDSEN, B. T.; ØISETH, O. The effects of an extended sensitivity analysis of sensor configurations for bridge damage detection using experimental data. In: *Proceedings of the Society for Experimental Mechanics Annual Conference and Exposition*, p. 91–98, 2024.
9. DEL POZO, G. A.; SVENDSEN, B. T.; PETERSEN, Ø. W.; ØISETH, O. Explicit uncertainty propagation in Mahalanobis squared distance for reliable damage detection of bridges using experimental data. *Journal of Civil Structural Health Monitoring*, v. 15, p. 4195–4218, 2025. DOI: [10.1007/s13349-025-01035-4](https://doi.org/10.1007/s13349-025-01035-4).
10. HU, J.; CHE, G.; WANG, Y. A Group-Aware Data Quality Stress Testing Framework for Bridge Structural Health Monitoring: Evidence from the Vänersborg and Z24 Datasets. *Infrastructures*, v. 11, n. 10, 2026. DOI: [10.3390/infrastructures11100344](https://doi.org/10.3390/infrastructures11100344).
11. DENG, F.; TAO, X.; WEI, P.; WEI, S. A robust deep learning-based damage identification approach for SHM considering missing data. *arXiv:2304.00040*, 2023. DOI: [10.48550/arXiv.2304.00040](https://doi.org/10.48550/arXiv.2304.00040).
12. GEIFMAN, Y.; EL-YANIV, R. Selective Classification for Deep Neural Networks. In: *Advances in Neural Information Processing Systems*, v. 30, 2017. Disponível em: [https://proceedings.neurips.cc/paper/2017/hash/4a8423d5e91fda00bb7e46540e2b0cf1-Abstract.html](https://proceedings.neurips.cc/paper/2017/hash/4a8423d5e91fda00bb7e46540e2b0cf1-Abstract.html).
13. GUO, C.; PLEISS, G.; SUN, Y.; WEINBERGER, K. Q. On Calibration of Modern Neural Networks. In: *Proceedings of the 34th International Conference on Machine Learning*, PMLR 70, p. 1321–1330, 2017. Disponível em: [https://proceedings.mlr.press/v70/guo17a.html](https://proceedings.mlr.press/v70/guo17a.html).
14. LYDAKIS, E.; KOSS, H.; BRINCKER, R.; AMADOR, S. D. R. Data-driven sensor fault diagnosis for vibration-based structural health monitoring under ambient excitation. *Measurement*, v. 237, 115232, 2024. DOI: [10.1016/j.measurement.2024.115232](https://doi.org/10.1016/j.measurement.2024.115232).
15. KU LEUVEN. Z24 Bridge benchmark: documentação dos ensaios, monitoramento ambiental, danos progressivos e condições de acesso. Disponível em: [https://bwk.kuleuven.be/bwm/z24](https://bwk.kuleuven.be/bwm/z24). Acesso em: nov. 2026.
16. SVENDSEN, B. T.; ØISETH, O.; FRØSETH, G. T.; RØNNQUIST, A. A hybrid structural health monitoring approach for damage detection in steel bridges under simulated environmental conditions using numerical and experimental data. *Structural Health Monitoring*, v. 22, n. 1, p. 540–561, 2023. DOI: [10.1177/14759217221098998](https://doi.org/10.1177/14759217221098998).
17. PECC/UnB. Linhas de Pesquisa. Disponível em: [http://www.peccft.unb.br/index.php/pt/quem-somos/linhas-de-pesquisa](http://www.peccft.unb.br/index.php/pt/quem-somos/linhas-de-pesquisa). Acesso em: nov. 2026.

---
