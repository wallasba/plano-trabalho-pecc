# Plano de Trabalho e Pesquisa — versão inicial para discussão

**Título provisório:** Confiabilidade e generalização de métodos de aprendizado de máquina para monitoramento da saúde estrutural de pontes  
**Área de concentração proposta:** Estruturas  
**Linha de pesquisa proposta:** Métodos Numéricos e Computacionais Aplicados à Engenharia (Estruturas), sujeita à confirmação pelo PECC  
**Estado:** proposta inicial; pergunta, dados, orientação e originalidade ainda dependem de validação  
**Data:** novembro de 2026

> **Nota:** Esta versão segue as seis seções previstas no Edital PECC nº 01/2027. Ainda requer revisão bibliográfica sistemática, confirmação de orientação e linha, auditoria de dados e ajuste final à formatação de até 10 páginas. As hipóteses são propostas, não resultados obtidos. A versão para submissão deve identificar o candidato somente na capa e manter as demais páginas anônimas.

## 1. Introdução

O monitoramento da saúde estrutural (Structural Health Monitoring — SHM) utiliza medições de sensores para acompanhar a resposta de estruturas e apoiar a identificação de mudanças em seu comportamento. Em pontes, sinais de aceleração, deformação, deslocamento e variáveis ambientais podem contribuir para essa avaliação. Entretanto, mudanças observadas nos sinais podem decorrer tanto de dano quanto de temperatura, vento, tráfego, alterações operacionais, ruído ou falhas de sensores. Um modelo que confunda essas causas pode produzir alertas indevidos ou não sinalizar mudanças relevantes.

Métodos estatísticos, de identificação de sistemas e de aprendizado de máquina têm sido aplicados a problemas de monitoramento e detecção de dano. Benchmarks estruturais, incluindo os reunidos pelo DataCenterHub/NEES, promovem comparação de algoritmos, mas incluem problemas heterogêneos e, em alguns casos, dados de simulação. Conjuntos experimentais de pontes como Hell Bridge Test Arena (HBTA) e Z24 oferecem oportunidades distintas: a HBTA contém estados estruturais de referência e danos impostos em uma ponte de aço em escala real; Z24 combina monitoramento de longo prazo com variabilidade ambiental e ensaios progressivos de dano, sujeito a solicitação e termos próprios de uso.

**Pergunta de pesquisa:** como avaliar a confiabilidade de métodos de aprendizado de máquina para identificar mudanças estruturais em pontes quando variam as condições ambientais e operacionais ou a disponibilidade dos sensores, e em que condições esses métodos devem sinalizar incerteza em vez de emitir uma classificação conclusiva?

A hipótese de trabalho é que um protocolo que controle separadamente as fontes de variação, respeite as unidades independentes dos dados e avalie incerteza e risco de erro produzirá uma caracterização mais confiável do desempenho que comparações baseadas apenas em métricas médias. Métodos de calibração, detecção de mudança ou decisão seletiva serão investigados somente após a auditoria dos dados e a revisão do estado da arte. A hipótese poderá ser rejeitada se os ganhos não se reproduzirem, não superarem baselines simples ou dependerem de cenários artificiais pouco representativos.

## 2. Justificativa

O problema é relevante para a engenharia estrutural porque o uso de dados de monitoramento exige distinguir mudanças relacionadas à estrutura de variações ambientais, operacionais e instrumentais. A pesquisa buscará produzir evidência sobre confiabilidade e limites de métodos computacionais, sem equiparar uma anomalia estatística a um diagnóstico de dano ou a uma conclusão sobre segurança estrutural.

A contribuição científica potencial não é simplesmente aplicar uma rede neural a um conjunto de sinais. A lacuna candidata está na avaliação reproduzível da relação entre mudança de condições, risco de erro, incerteza e custo de adaptação em problemas de SHM de pontes. Essa lacuna e a originalidade de qualquer método serão verificadas por revisão bibliográfica recente e comparação com estudos que já utilizam os mesmos benchmarks. O trabalho deve avançar além de uma comparação de modelos prontos; se a auditoria não sustentar uma contribuição metodológica nova, o foco será revisto antes de reivindicar originalidade.

A estratégia de dados em etapas permite iniciar com benchmarks acessíveis, documentar restrições de acesso e testar hipóteses sem depender inicialmente de uma parceria nacional. A relevância para o Brasil está no desenvolvimento de métodos e protocolos que possam ser avaliados futuramente em estruturas brasileiras. Não se alegará validação nacional sem dados locais autorizados, representativos e avaliados independentemente.

A aderência proposta ao PECC está na aplicação de métodos computacionais, estatísticos e de identificação de sistemas a estruturas. O enquadramento formal na área de Estruturas e em linha de pesquisa vigente, bem como a orientação ou coorientação, deverá ser confirmado com o programa. A experiência do candidato em engenharia estrutural, matemática, ciência de dados, Python e dados de infraestrutura é compatível com o tema; a pesquisa permitirá aprofundar aprendizado de máquina, deep learning e inferência estatística. A análise geoespacial poderá caracterizar a proveniência e a representatividade dos dados se os metadados permitirem, sem constituir um segundo eixo independente.

## 3. Objetivos

### Objetivo geral

Desenvolver e avaliar um protocolo reproduzível para analisar a confiabilidade e a generalização de métodos de aprendizado de máquina aplicados ao monitoramento da saúde estrutural de pontes sob variações ambientais, operacionais e instrumentais.

### Objetivos específicos

1. Fazer triagem sistemática dos registros de dados nas páginas NEES e post-NEES do DataCenterHub e auditar em profundidade os conjuntos candidatos quanto a acesso, licença, documentação, sensores, estados estruturais, metadados e publicações associadas.
2. Selecionar uma tarefa SHM e uma base principal com estados de referência e critérios de avaliação reproduzíveis.
3. Reproduzir baselines estatísticos, de identificação de sistemas e de aprendizado de máquina adequados à tarefa selecionada.
4. Avaliar o efeito de variações documentadas nos dados e de cenários controlados de ruído ou indisponibilidade de sensores, sem confundi-los com dano observado.
5. Investigar calibração, quantificação de incerteza ou decisão seletiva e comparar seus efeitos sobre risco, cobertura e custo com baselines fortes.
6. Testar validação externa somente quando tarefa, variáveis e critérios forem suficientemente compatíveis; documentar limites de transferência entre estruturas.
7. Avaliar a viabilidade de uma aplicação brasileira por parceria e dados autorizados, sem pressupor acesso ou representatividade antes de sua confirmação.

## 4. Revisão da Literatura

A revisão será organizada em cinco eixos: (i) SHM de pontes e identificação de sistemas; (ii) influência ambiental e operacional sobre características dinâmicas; (iii) detecção de dano e distinção entre mudança estrutural e falha de instrumentação; (iv) aprendizado de máquina, mudança de domínio, calibração e incerteza; e (v) desenho de benchmarks, validação estatística e reprodutibilidade.

O DataCenterHub mantém um conjunto de problemas de controle e monitoramento estrutural propostos por diferentes grupos. Sua documentação registra que os problemas têm sido extensamente estudados e incluem arquivos MATLAB, modelos e dados de natureza diversa. A triagem dos catálogos NEES e post-NEES deve, portanto, preceder a seleção de casos: nem todo recurso é SHM, ponte, monitoramento de dano ou dado experimental. O registro 264 é um catálogo de projetos potencialmente úteis para SHM/model updating, não uma base uniforme.

A HBTA é uma instalação experimental em escala real, com estados sem dano e danos impostos, sinais de resposta dinâmica e documentação associada. O Z24 reúne monitoramento de longo prazo com condições ambientais e ensaios de dano progressivo, mas o acesso deve ser solicitado à instituição responsável e está sujeito aos respectivos termos. As bases NTNU de pontes monitoradas podem apoiar estudos de variabilidade ambiental e operacional; sem rótulos de dano compatíveis, não serão tratadas como testes supervisionados de detecção de dano.

A revisão aprofundará publicações sobre cada conjunto selecionado, métodos de detecção e normalização ambiental, avaliação sob perda de sensores, quantificação de incerteza e estudos publicados até 2026. A contribuição final será formulada somente depois de identificar o que já foi testado nesses dados e quais limitações permanecem.

## 5. Metodologia

### 5.1 Desenho e auditoria dos dados

A pesquisa será quantitativa, computacional e experimental, com etapas de triagem, auditoria, reprodução, avaliação controlada e validação externa condicional. A triagem abrangerá os registros de [Legacy/NEES](https://datacenterhub.org/nees.html) e [post-NEES](https://datacenterhub.org/post-nees.html). Para cada registro serão anotados identificador, descrição, tipo de estrutura, tipo de dado, finalidade, acesso, documentação e pertinência potencial a SHM de pontes. A análise detalhada será limitada aos candidatos pertinentes.

Candidatos iniciais incluem [DataCenterHub 257 — Structural Control and Monitoring Benchmark Problems](https://datacenterhub.org/resources/257), [DataCenterHub 264 — Projects Suitable for SHM and Model Updating Research](https://datacenterhub.org/resources/264), [Hell Bridge Test Arena](https://zenodo.org/records/14632942), [Z24](https://bwk.kuleuven.be/bwm/z24) e o [portal de dados abertos da NTNU](https://www.ntnu.edu/kt/open-data). A seleção não está fechada. Serão verificados arquivos efetivamente disponíveis, licença, formatos, variáveis, amostragem, estados de dano, condições ambientais e operacionais, estrutura de agrupamento, documentação, referências, tamanho e requisitos de software.

### 5.2 Portões de decisão

1. **Acesso e termos:** se arquivos ou termos de uso impedirem os experimentos previstos, excluir ou substituir a base.
2. **Tarefa identificável:** se não houver estados de referência, variáveis e rótulos interpretáveis, não alegar detecção supervisionada de dano; reformular para a tarefa suportada pelos dados.
3. **Independência e vazamento:** estabelecer partições por ensaio, estado, período ou estrutura, conforme a unidade independente disponível. Se não for possível, explicitar a limitação e não tratar amostras correlacionadas como observações independentes.
4. **Variação ambiental:** só testar efeitos ambientais se houver variáveis ou períodos documentados adequados. Ruído e sensores ausentes introduzidos artificialmente serão identificados como testes de estresse, não como evidência de condições reais.
5. **Comparabilidade externa:** só fazer avaliação entre bases quando a tarefa e as variáveis forem defensáveis. Não fundir sinais incompatíveis nem alegar transferência de domínio apenas por aplicar o mesmo código a bases diferentes.
6. **Originalidade:** se a revisão revelar que a lacuna candidata já foi respondida, reformular a contribuição antes de desenvolver o método.
7. **Aplicação brasileira:** avançar para validação nacional somente com autorização, metadados e avaliação independente adequados; caso contrário, manter essa etapa como perspectiva futura.

### 5.3 Baselines e avaliação

Após a auditoria será selecionado um benchmark principal. Serão reproduzidos métodos de referência descritos na documentação e na literatura, incluindo ao menos uma abordagem estatística ou de identificação de sistemas e uma abordagem de aprendizado de máquina apropriada. Deep learning será incluído somente se tamanho, estrutura e quantidade de dados justificarem seu uso. O orçamento computacional e o pré-processamento serão registrados.

As métricas dependerão da tarefa final. Para classificação de estado poderão incluir sensibilidade, especificidade, precisão, revocação, F1 e medidas balanceadas; para detecção de anomalia, curvas de desempenho e taxas de falso alarme; para confiabilidade, calibração e risco versus cobertura, quando aplicáveis. Serão apresentados resultados por cenário e classe, não apenas médias agregadas. O custo incluirá tempo, memória e quantidade de dados rotulados para adaptação.

Sementes, divisões, transformações, hiperparâmetros e limiares serão documentados. A unidade de reamostragem e os intervalos de confiança respeitarão a estrutura dos dados; não se fará inferência tratando cada janela temporal ou amostra correlacionada como independente. A eventual revisão de casos será feita com especialista em estruturas/SHM.

### 5.4 Python, estatística e componente geoespacial

Python será utilizado para ingestão, validação, processamento, experimentação, análise estatística e documentação reproduzível. Metadados geoespaciais poderão apoiar a descrição de localização, tipo estrutural e cobertura dos conjuntos, caso existam e possam ser usados. Essa análise não substituirá a validação estrutural e não será usada para inferir representatividade nacional a partir de poucas pontes estrangeiras.

### 5.5 Etapas, recursos e riscos

- **Etapa 1:** revisão focalizada, triagem integral dos catálogos NEES/post-NEES e auditoria aprofundada dos candidatos.
- **Etapa 2:** escolha da tarefa e base principal; reprodução dos baselines e fixação do protocolo estatístico.
- **Etapa 3:** testes de confiabilidade, variação ambiental/instrumental e método candidato, se justificado.
- **Etapa 4:** avaliação externa compatível e, se houver dados/parceria, piloto brasileiro.
- **Etapa 5:** síntese, publicação, código e documentação conforme licenças, redação da tese.

As bases de sinais podem ser processadas com CPU e armazenamento moderados, mas arquivos brutos ou alta frequência podem exigir espaço adicional. O dimensionamento será feito com piloto de leitura, memória e tempo; GPU não será requisito presumido. Riscos centrais incluem dados indisponíveis, benchmark antigo ou muito explorado, falta de rótulos, escassez de estruturas independentes, efeitos ambientais não observáveis e ausência de acesso a dados nacionais. As decisões de contingência estão definidas nos portões acima.

## 6. Referências Bibliográficas

1. DYKE, S. J. et al. *NEES: Database for Structural Control and Monitoring Benchmark Problems*. DataCenterHub, 2015. DOI: [10.4231/D3Q52FC7T](https://doi.org/10.4231/D3Q52FC7T).
2. SONG, W.; HERNÁNDEZ, L.; CATLIN, A. C. *NEES: Projects Suitable for SHM and Model Updating Research*. DataCenterHub, 2015. DOI: [10.4231/D3ZW18T26](https://doi.org/10.4231/D3ZW18T26).
3. SVENDSEN, B. T. et al. *A data set from an extensive experimental benchmark study of the Hell Bridge Test Arena subject to imposed damage*. Journal of Structural Engineering, 2025. DOI: [10.1061/JSENDH.STENG-14818](https://doi.org/10.1061/JSENDH.STENG-14818). Conjunto de dados: [Zenodo 14632942](https://doi.org/10.5281/zenodo.14632942).
4. PEETERS, B.; DE ROECK, G. *One-year monitoring of the Z24-Bridge: environmental effects versus damage events*. Earthquake Engineering & Structural Dynamics, 2001. Referências e acesso aos dados: [KU Leuven — Z24](https://bwk.kuleuven.be/bwm/z24).
5. FENERCİ, A. et al. *Data Set for Long-Term Wind and Acceleration Monitoring of the Hardanger Bridge*. Journal of Structural Engineering, 2021. DOI: [10.1061/(ASCE)ST.1943-541X.0002997](https://doi.org/10.1061/(ASCE)ST.1943-541X.0002997).
6. KVALE, K. A. et al. *Data set from long-term wave, wind and response monitoring of the Bergsøysund Bridge*. Zenodo, 2022. [Registro e DOI](https://zenodo.org/records/8051201).
7. LIMONGELLI, M. P. et al. *SCSHM benchmark study on bridge in-service structural monitoring*. Journal of Civil Structural Health Monitoring, 2025. DOI: [10.1007/s13349-024-00846-1](https://doi.org/10.1007/s13349-024-00846-1). Acesso ao conjunto sujeito às condições informadas pelos autores.

> **Nota bibliográfica:** referências científicas adicionais sobre detecção de dano, efeitos ambientais, mudança de domínio, incerteza e avaliação estatística devem ser incorporadas após a revisão sistemática focalizada. A citação do conjunto ou benchmark não comprova, por si só, que ele seja adequado à tarefa proposta.

---

**Validações pendentes:** linha e orientação vigentes no PECC; auditoria dos registros e arquivos DataCenterHub; acesso e termos do Z24; adequação do Hell Bridge à pergunta final; revisão da originalidade frente à literatura recente; acesso a especialista em SHM; disponibilidade de dados brasileiros e metadados geoespaciais.
