# Plano de Trabalho e Pesquisa — versão preliminar para validação

**Título provisório:** Confiabilidade de modelos de visão computacional para inspeção de danos em pontes sob mudança de domínio  
**Área de concentração proposta:** Estruturas  
**Linha de pesquisa proposta:** Métodos Numéricos e Computacionais Aplicados à Engenharia (Estruturas), sujeita à confirmação pelo PECC  
**Candidato:** inserir apenas na capa da versão para submissão  
**Estado:** rascunho científico; bases e orientação ainda não validadas  
**Data:** novembro de 2026

> **Nota de revisão.** Este texto segue as seis seções exigidas pelo Edital PECC nº 01/2027. Ainda não foi diagramado nem aferido em A4, Times New Roman 12 e espaçamento 1,5. As hipóteses e contribuições são propostas de pesquisa, não resultados obtidos. As referências abaixo compõem uma revisão inicial, que deverá ser ampliada e atualizada antes da submissão.

## 1. Introdução

A inspeção visual de pontes produz imagens em condições variadas de iluminação, distância, resolução, material e estado de conservação. Sistemas de visão computacional podem auxiliar a localização de fissuras, desplacamentos, corrosão e outras manifestações aparentes. Entretanto, a utilidade do sistema depende de seu comportamento em estruturas e condições diferentes das usadas no treinamento. Uma previsão com alta confiança e erro em uma nova ponte pode induzir uma priorização inadequada da revisão humana. O apoio computacional deve, portanto, apresentar evidências visuais localizáveis, desempenho mensurado fora do conjunto de desenvolvimento e indicação de incerteza [1–3].

O conjunto **dacl10k** reuniu 9.920 imagens de inspeções reais e estabeleceu uma referência de segmentação multirrótulo de danos e componentes de pontes [1]. O desafio associado mostrou avanços na segmentação, mas também diferenças substanciais entre classes, sobretudo nas raras ou visualmente difíceis [2]. O **dacl1k**, concebido para testar modelos em imagens de inspeção heterogêneas, mostrou que bom desempenho nas bases de desenvolvimento não assegura igual resultado em um conjunto externo [3]. Em visão computacional geral, pesquisas demonstraram que robustez de segmentação, calibração de probabilidades e identificação de erros podem evoluir de forma diferente quando o domínio muda [4, 5].

**Pergunta de pesquisa:** como avaliar e melhorar a confiabilidade de modelos que identificam danos visuais em pontes quando variam a estrutura, a origem dos dados ou as condições de aquisição, mantendo explícitos o custo computacional e os limites de generalização?

A tese propõe investigar a relação entre **desempenho**, **incerteza** e **decisão de encaminhar casos à revisão humana**. A hipótese central é que um procedimento que combine avaliação externa rigorosa, calibração apropriada e decisão seletiva baseada em incerteza reduza erros críticos sob mudança de domínio em comparação com modelos avaliados apenas pela acurácia ou interseção sobre união no conjunto de origem. A hipótese será rejeitada se os ganhos não se reproduzirem em dados externos ou se dependerem de perda desproporcional de cobertura, custo ou desempenho em classes relevantes.

## 2. Justificativa

O problema possui relevância para a engenharia estrutural porque a documentação de manifestações visuais é uma etapa da inspeção, embora a imagem isolada não determine a segurança ou a capacidade resistente da ponte. A proposta busca apoiar a triagem e a revisão por especialistas, com localização da evidência e limites de confiança, sem automatizar diagnósticos estruturais conclusivos. O enfoque em generalização e incerteza responde à necessidade de avaliar o comportamento em imagens provenientes de outras pontes e ambientes [1–4].

A relevância científica não decorre somente de aplicar uma rede neural ao dacl10k. Já existem arquiteturas, métodos de calibração e estudos de adaptação. A lacuna candidata é a falta de uma avaliação **integrada e reproduzível**, específica da inspeção de pontes, que relacione deslocamento de domínio, classes de dano, incerteza, cobertura de casos encaminhados à revisão humana e custo de adaptação. A existência e a extensão dessa lacuna serão confirmadas na revisão bibliográfica completa; estudos recentes que já abordem partes dela serão usados como comparadores, não ignorados [2, 4–6].

O projeto pode ser conduzido remotamente com dados públicos e código aberto. Não exige coleta em campo ou treinamento de um modelo fundacional desde o início. Seu impacto potencial está em fornecer evidência metodológica para pesquisadores e critérios mais transparentes para avaliar ferramentas de apoio à inspeção. O resultado será limitado aos domínios efetivamente testados; sem amostra brasileira representativa, não será apresentado como validação de uso em obras de arte especiais brasileiras.

A aderência proposta ao PECC está na aplicação de métodos computacionais a um problema de inspeção de estruturas, com análise estatística de confiabilidade e interpretação dos erros segundo manifestações de dano. A linha de pesquisa e a composição de orientação deverão ser confirmadas com o programa. A participação de especialista em pontes é necessária para revisar a taxonomia e uma amostra de erros; colaboração em Computação ou Ciência de Dados é desejável para a parte metodológica.

## 3. Objetivos

### Objetivo geral

Desenvolver e avaliar um procedimento reproduzível para identificar danos aparentes em imagens de pontes com estimativa de confiabilidade sob mudança de domínio, quantificando quando o modelo deve encaminhar a imagem ou região à revisão humana.

### Objetivos específicos

1. Auditar bases públicas quanto a acesso, licença, proveniência, rótulos, duplicatas, identificação de estruturas e compatibilidade entre tarefas.
2. Estabelecer um protocolo de avaliação que separe desenvolvimento e teste por ponte ou origem identificável e inclua dados externos quando houver classes compatíveis.
3. Reproduzir modelos de referência de custo moderado e medir desempenho, calibração, detecção de erros e diferenças entre classes e domínios.
4. Investigar um método de calibração e encaminhamento seletivo de casos incertos; comparar sua efetividade e custo com alternativas publicadas.
5. Examinar se adaptação eficiente com quantidade limitada de exemplos rotulados do novo domínio melhora a confiabilidade sem degradar outras classes ou elevar excessivamente o custo.
6. Documentar falhas, limites de transferência e condições para uso como apoio à inspeção, com revisão técnica de uma amostra por especialista.

## 4. Revisão da Literatura

Flotzinger, Rösch e Braml [1] apresentaram o dacl10k como referência de segmentação multirrótulo com imagens de inspeções reais, danos e componentes. O desafio posterior [2] reuniu soluções com arquiteturas e estratégias variadas e mostrou que a pontuação agregada oculta diferenças importantes entre classes. Esses trabalhos estabelecem bases e comparadores relevantes, mas a métrica de segmentação, isoladamente, não responde quando uma previsão errada deve ser revista por um inspetor.

O estudo do dacl1k [3] enfatizou a avaliação em imagens heterogêneas e de fora das bases usadas para desenvolvimento. Sua tarefa é classificação multirrótulo, enquanto dacl10k oferece máscaras; uma comparação exige converter previsões para uma tarefa comum e conferir cuidadosamente a equivalência dos rótulos. O CODEBRIM [7] oferece imagens e anotações de defeitos de concreto em diferentes versões, e o repositório Cambridge [8] pode apoiar um piloto externo menor. A utilidade efetiva dessas bases depende de auditoria dos arquivos, das licenças, da origem das imagens e da possível sobreposição entre conjuntos.

De Jorge et al. [4] avaliaram robustez e incerteza em segmentação semântica sob mudança de domínio e encontraram que melhoria de segmentação não implica, necessariamente, melhor calibração. Wang, Gong e Wang [5] estudaram calibração de modelos de segmentação e propuseram um método de referência. Trabalhos de adaptação entre domínios [6] mostram possibilidades metodológicas adicionais. Esses resultados são gerais e exigem validação cuidadosa para imagens de pontes, classes raras, rótulos sobrepostos e diferentes unidades de inspeção. A revisão final examinará também pesquisas de 2025–2026 sobre inspeção de pontes, segmentação confiável, adaptação eficiente e avaliação seletiva, para delimitar uma contribuição efetivamente nova.

## 5. Metodologia

### 5.1 Desenho e critérios de viabilidade

A pesquisa será quantitativa e experimental, com etapas de auditoria, reprodução de referências, desenvolvimento metodológico e avaliação externa. A base principal candidata é o **dacl10k v2** [1, 9]. O dacl1k [3], o CODEBRIM [7] e o Cambridge [8] serão examinados como conjuntos externos. A inclusão de cada um dependerá de quatro condições: acesso e uso permitidos, rótulos interpretáveis, ausência de sobreposição não controlada com os dados de treinamento e definição de uma tarefa compartilhada. A licença CC BY-NC 4.0 indicada no toolkit do dacl10k será respeitada [9]. Dados não serão redistribuídos quando os termos não permitirem.

A tarefa principal será a **segmentação multirrótulo** de manifestações visuais no dacl10k. Para avaliação externa, uma tarefa secundária de **presença de dano por imagem** poderá ser derivada das máscaras previstas, usando apenas classes que tenham equivalência documentada com os rótulos da base externa. Resultados de segmentação e classificação serão relatados separadamente. Caso não haja base externa compatível, a tese limitará a alegação a mudanças de domínio que possam ser identificadas dentro da base principal; o desenho será revisto antes de afirmar generalização entre bases.

### 5.2 Auditoria, partições e baselines

O inventário registrará versões, arquivos, checksums, tamanho, licença, amostras por classe, origem, identificação de ponte, formatos e anotações. Serão investigadas duplicatas exatas e visualmente semelhantes. Quando houver identificador de ponte, todas as suas imagens permanecerão na mesma partição. Se isso não for possível, a unidade de agrupamento será a origem conhecida e a limitação será explicitada. O teste externo e qualquer conjunto final permanecerão isolados da escolha de hiperparâmetros, limiares e calibração.

Serão reproduzidos um baseline de segmentação da publicação do dacl10k [1], um modelo leve competitivo do desafio [2] e pelo menos um método publicado de calibração [4 ou 5]. O conjunto exato de arquiteturas será fechado após verificar código, pesos, licenças e recursos, mantendo o mesmo pré-processamento e orçamento experimental nas comparações. A simples superioridade em uma única divisão não será considerada contribuição de doutorado.

### 5.3 Método candidato e hipóteses testáveis

O método candidato combinará **calibração por classe ou região** com um critério de **encaminhamento seletivo**: previsões com evidência insuficiente serão marcadas para revisão. A definição será orientada por experimentos iniciais e comparada a limiares globais, escalonamento de temperatura e estratégias publicadas. O objetivo não é afirmar que a incerteza identifica todo erro, mas medir seu poder de discriminação e a troca entre erros remanescentes e proporção de casos encaminhados.

H1: sob mudança de domínio, um procedimento calibrado e seletivo reduzirá a taxa de erros nos casos aceitos para uma mesma cobertura, comparado a baselines sem calibração. H2: uma adaptação eficiente com poucos exemplos do novo domínio poderá melhorar a relação entre desempenho e custo; será descartada se o ganho não superar métodos mais simples ou não se reproduzir. O método final só será apresentado como original depois de confronto sistemático com a literatura recente.

### 5.4 Métricas e análise estatística

Para segmentação, serão relatados IoU/Dice por classe e média, além de sensibilidade de classes relevantes. Para a tarefa externa por imagem, serão relatadas precisão, revocação e medidas apropriadas ao desbalanceamento por classe. A confiabilidade será avaliada por calibração de probabilidades, capacidade de identificar erros e curvas de **risco versus cobertura**. O custo incluirá memória, tempo de treinamento/inferência e número de exemplos rotulados necessários à adaptação.

As comparações usarão repetições com sementes fixadas e intervalos de confiança por reamostragem da unidade independente disponível: ponte, origem ou grupo documentado. A reamostragem por pixels individuais não será usada para inferir independência entre estruturas. Serão publicados resultados por classe e domínio, não apenas médias. Limiares e hiperparâmetros serão definidos no desenvolvimento; o conjunto final será usado uma única vez para avaliação confirmatória. Uma amostra de falsos negativos, falsos positivos e previsões muito confiantes será revisada com especialista em engenharia de pontes, respeitando o escopo visual dos rótulos.

### 5.5 Cronograma, recursos e riscos

**Etapa 1:** revisão sistemática focalizada, auditoria das bases e definição de tarefa, partições e baselines. **Etapa 2:** reprodução e estudo de robustez, calibração e erros. **Etapa 3:** desenvolvimento do método e experimentos de adaptação eficiente. **Etapa 4:** avaliação externa, análise estatística, revisão técnica, artigos e tese. A distribuição em semestres será acordada com o orientador e com os prazos regimentais do PECC.

Para a auditoria e modelos clássicos, uma estação com CPU de 4–8 núcleos, 16 GB de RAM e SSD com espaço livre suficiente é uma referência inicial. Para treinar e repetir modelos de visão de porte moderado, estima-se como configuração de trabalho 32 GB de RAM, SSD de 1 TB e GPU com 12–16 GB de VRAM, própria ou compartilhada. São **estimativas**, não requisitos medidos. Um piloto registrará pico de RAM/VRAM, tempo e armazenamento antes de fixar o orçamento experimental. Modelos maiores ou buscas extensas dependerão de infraestrutura universitária ou nuvem. O treinamento de um modelo fundacional do zero não integra o escopo.

Os riscos principais são: ausência de identificadores por ponte; rótulos incompatíveis entre bases; classes raras; sobreposição de imagens entre conjuntos; limitações de licença; e ganhos que desapareçam em teste externo. As respostas planejadas são, respectivamente, agrupamento pela origem disponível com limitação declarada; restrição a classes equivalentes; análise por classe e incerteza; deduplicação; uso dentro dos termos; e rejeição da hipótese ou reformulação do método. Se os dados não sustentarem avaliação externa confiável, a proposta deverá ser reavaliada com a orientação antes de manter alegações de generalização.

## 6. Referências Bibliográficas

1. FLOTZINGER, J.; RÖSCH, P. J.; BRAML, T. [dacl10k: Benchmark for Semantic Bridge Damage Segmentation](https://openaccess.thecvf.com/content/WACV2024/html/Flotzinger_dacl10k_Benchmark_for_Semantic_Bridge_Damage_Segmentation_WACV_2024_paper.html). *WACV*, 2024.
2. FLOTZINGER, J. et al. [Dacl-Challenge: Semantic Segmentation During Visual Bridge Inspections](https://openaccess.thecvf.com/content/WACV2024W/DACL/papers/Flotzinger_Dacl-Challenge_Semantic_Segmentation_During_Visual_Bridge_Inspections_WACVW_2024_paper.pdf). *WACV Workshops*, 2024.
3. FLOTZINGER, J. et al. [dacl1k: Real-world bridge damage dataset putting open-source data to the test](https://www.sciencedirect.com/science/article/pii/S0952197624012648). *Engineering Applications of Artificial Intelligence*, v. 137, 109106, 2024.
4. DE JORGE, P. et al. [Reliability in Semantic Segmentation: Are We on the Right Track?](https://openaccess.thecvf.com/content/CVPR2023/html/de_Jorge_Reliability_in_Semantic_Segmentation_Are_We_on_the_Right_Track_CVPR_2023_paper.html). *CVPR*, 2023.
5. WANG, D.; GONG, B.; WANG, L. [On Calibrating Semantic Segmentation Models: Analyses and an Algorithm](https://openaccess.thecvf.com/content/CVPR2023/html/Wang_On_Calibrating_Semantic_Segmentation_Models_Analyses_and_an_Algorithm_CVPR_2023_paper.html). *CVPR*, 2023.
6. ZHAO, X. et al. [Unsupervised Domain Adaptation for Semantic Segmentation With Pseudo Label Self-Refinement](https://openaccess.thecvf.com/content/WACV2024/html/Zhao_Unsupervised_Domain_Adaptation_for_Semantic_Segmentation_With_Pseudo_Label_Self-Refinement_WACV_2024_paper.html). *WACV*, 2024.
7. MUNDT, M. et al. [CODEBRIM: COncrete DEfect BRidge IMage Dataset](https://zenodo.org/records/2620293). Zenodo, 2019. DOI: 10.5281/zenodo.2620293.
8. HUETHWOHL, P. [Cambridge Bridge Inspection Dataset](https://www.repository.cam.ac.uk/items/f73994b0-b86f-4007-b0b0-cd0179c6f865/full). University of Cambridge, 2017. DOI: 10.17863/CAM.13813.
9. FLOTZINGER, J. et al. [dacl10k toolkit e dados](https://github.com/phiyodr/dacl10k-toolkit). Repositório oficial, consulta em novembro de 2026.

---

**Pontos para validação com o candidato e orientadores:** aderência da pergunta à linha atual do PECC; originalidade após revisão de 2025–2026; acesso a dados externos comparáveis; disponibilidade de revisão especializada e GPU; e possibilidade de formular uma contribuição metodológica publicável além do protocolo de avaliação.
