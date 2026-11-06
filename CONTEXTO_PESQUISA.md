# Contexto da pesquisa — PECC

## Objetivo

Preparar uma proposta de trabalho e pesquisa para candidatura ao doutorado no PECC, com orientação principal em Computação ou coorientação na área. O interesse é construir uma base forte em computação, inteligência artificial — incluindo IA generativa — e estatística, aplicadas a problemas de inspeção e monitoramento de pontes/obras de arte especiais (OAEs). A pesquisa deve priorizar dados abertos e públicos e ser compatível com execução remota.

## Direção de pesquisa em discussão

**Direção prioritária atual (provisória):** confiabilidade e generalização de métodos de aprendizado de máquina para monitoramento da saúde estrutural (SHM) de pontes sob variações ambientais, operacionais e instrumentais. A pergunta candidata é: como avaliar a confiabilidade desses métodos quando mudam as condições ambientais e operacionais ou a disponibilidade dos sensores, e quando o sistema deve sinalizar incerteza em vez de emitir uma classificação conclusiva?

A contribuição deve ir além de comparar modelos prontos: pretende-se construir um protocolo reproduzível e investigar, após auditoria e revisão de originalidade, estratégias de calibração, quantificação de incerteza, detecção de mudança ou decisão seletiva. A rota visual (dacl10k/dacl1k e bases relacionadas) permanece como alternativa; não se propõe fusão de imagens e sensores, pois não há pareamento confirmado entre esses acervos.

A análise estatística deve respeitar a unidade independente real (ensaio, período, estrutura ou grupo documentado), evitar vazamento, reportar resultados por cenário e incluir incerteza, falsos alarmes, custo e limites de generalização. Ruído ou sensores removidos artificialmente devem ser descritos como testes de estresse, não como observações de condições reais.

## Dados e repositórios para investigar

- [DataCenterHub / Legacy NEES](https://datacenterhub.org/nees.html) e [post-NEES](https://datacenterhub.org/post-nees.html): catálogos heterogêneos de bases/projetos; deve-se fazer triagem de todos os registros e auditoria detalhada apenas dos candidatos a SHM/monitoramento de pontes. Não presumir licença, acesso ou adequação a partir do título.
- [DataCenterHub 257 — Structural Control and Monitoring Benchmark Problems](https://datacenterhub.org/resources/257): coleção de problemas de referência com documentação e arquivos MATLAB/simulação; inclui problemas diversos e já bastante estudados, não uma base uniforme de sinais de pontes.
- [DataCenterHub 264 — Projects Suitable for SHM and Model Updating Research](https://datacenterhub.org/resources/264): catálogo de projetos potencialmente relevantes a SHM/model updating; cada conjunto exige verificação própria.
- [NTNU — dados abertos de monitoramento estrutural](https://www.ntnu.edu/kt/open-data): séries de sensores de pontes como Hardanger, Bergsøysund, Gjemnessund e Hell; é mais apropriado para SHM e sinais do que para visão computacional de danos.
- [DesignSafe / NHERI Data Depot](https://www.designsafe-ci.org/): dados de engenharia de riscos naturais e ensaios experimentais, potencial fonte complementar.
- [Hell Bridge Test Arena — Zenodo](https://zenodo.org/records/14632942): ponte de aço em escala real, estados de referência e danos impostos, sinais dinâmicos em HDF5; candidata a base experimental principal, sujeita à auditoria da tarefa, documentação e licença.
- [Z24 — KU Leuven](https://bwk.kuleuven.be/bwm/z24): monitoramento de longo prazo, variabilidade ambiental e ensaios progressivos de dano; dados obtidos mediante solicitação e termos próprios.
- [dacl10k](https://openaccess.thecvf.com/content/WACV2024/papers/Flotzinger_dacl10k_Benchmark_for_Semantic_Bridge_Damage_Segmentation_WACV_2024_paper.pdf) e [Cambridge Bridge Inspection Dataset](https://www.repository.cam.ac.uk/items/f73994b0-b86f-4007-b0b0-cd0179c6f865): candidatos para inspeção visual anotada.

Não presumir que dados de sensores e imagens possam ser vinculados entre si. Rótulos de dano em imagens não equivalem a relatórios narrativos; geração de descrições técnicas precisaria de referências textuais adequadas e revisão por especialistas.

## Viabilidade, limites e recursos

A pesquisa deve ser **integralmente remota**: sem visitas a campo, coleta presencial, instalação de sensores ou ensaios físicos conduzidos pelo pesquisador. Usará dados digitais existentes, acessados remotamente e com uso autorizado. Solicitações de dados, parcerias, orientação e revisão técnica deverão ocorrer a distância. O processamento poderá ser local, em infraestrutura institucional acessada remotamente ou em nuvem; GPU não deve ser presumida antes de um piloto.

Sem dados brasileiros digitais, autorizados e adequados, os resultados devem ser apresentados como avaliação metodológica em bases internacionais, sem alegar validação para OAEs brasileiras. A aplicação nacional é condicional à obtenção remota dos dados, metadados e avaliação independente; não haverá campanha de campo como contingência. Python e estatística são centrais ao pipeline; análise geoespacial pode descrever proveniência e representatividade se os metadados permitirem, mas não será eixo autônomo. Combinar desde o início visão, sensores, geração de relatórios, previsão de deterioração e validação nacional ampliaria excessivamente a tese.

## Requisitos da proposta PECC

O PDF local identifica-se internamente como Edital PECC nº 01/2027. O plano de doutorado tem limite de 10 páginas, A4, espaço 1,5, Times New Roman 12, requer Introdução, Justificativa, Objetivos, Revisão da Literatura, Metodologia e Referências, e deve manter anônimas as páginas após a capa. A avaliação do plano é eliminatória (mínimo 7,0), com pesos 4/3/3 para relevância/bibliografia, metodologia e aderência ao PECC. A linha atual e a orientação devem ser confirmadas.

## Próximos passos

### Atualização de 05/11/2026

- Foi produzida a análise preliminar `analise-viabilidade-doutorado-pecc.md`, com matriz do edital, fontes de dados, pergunta central recomendada, alternativas em SHM, estimativa de infraestrutura e portões de viabilidade.
- Prioridade definida pelo candidato: **alto impacto e contribuição científica original com execução factível**. A complexidade metodológica é aceitável quando justificada; a pesquisa deve ocorrer remotamente com dados públicos e permitir uso de Python, IA, aprendizado de máquina, deep learning e estatística. PLN e IA agêntica são possibilidades subordinadas a hipótese e dados adequados.
- Pergunta candidata: confiabilidade, incerteza e adaptação eficiente de modelos de inspeção visual de danos em pontes sob mudança de domínio. É uma recomendação condicional, ainda dependente de auditoria dos arquivos, rótulos, identificadores de ponte e revisão de originalidade.
- O PDF local identifica-se internamente como **Edital PECC nº 01/2027**, com inscrições até 22/11/2026. O plano de até 10 páginas é eliminatório, mínimo 7,0; os critérios do Anexo A.2.1 pesam 4/3/3 para relevância/bibliografia, metodologia e aderência.
- O link antigo do DataCenterHub citado pelo candidato retornou 404 no acesso web; o registro preservado do benchmark está em https://datacenterhub.org/resources/257. Hell Bridge (2,5 GB) é uma opção de sinais com dano imposto. Bases de imagens e sensores não estão pareadas.
- **Próxima ação:** auditar os arquivos de dacl10k e ao menos uma base externa, confirmar licenças e unidades de agrupamento, executar piloto de recursos, então fechar a pergunta e redigir o plano para submissão.


1. Confirmar com possíveis orientadores a linha do PECC e a adequação do recorte à Computação.
2. Fazer inventário reproduzível de 2–4 bases candidatas: arquivos disponíveis, licença, número e tipo de amostras, rótulos, unidade de agrupamento (ponte), metadados e restrições.
3. Escolher uma pergunta principal e critérios de avaliação após a auditoria dos dados.
4. Definir o desenho estatístico, os baselines, validação entre domínios e métricas antes dos experimentos.
5. Redigir a proposta conforme o edital vigente, com contribuições, limitações e cronograma compatíveis com doutorado.

### Atualização de 05/11/2026 — mudança da rota prioritária

- Após comparação de aderência ao currículo e das bases candidatas, a rota prioritária passou a ser **SHM de pontes**, com foco em confiabilidade/generalização sob variação ambiental, operacional e instrumental. A proposta visual anterior permanece como alternativa, não como núcleo concorrente.
- Foi iniciado o rascunho `pre-projeto-doutorado-pecc-v2-shm.md`, organizado nas seis seções exigidas pelo Edital PECC nº 01/2027. Não está pronto para submissão: originalidade, dados, linha e orientação seguem pendentes.
- Os endereços `nees.html` e `post-nees.html` estão acessíveis; o link de visualizador específico anteriormente enviado retornou 404. O recurso 257 é uma coleção heterogênea de benchmarks; o recurso 264 é catálogo de projetos para SHM/model updating. Nenhum deve ser tratado como base única auditada.
- Candidatos externos: Hell Bridge Test Arena (dados experimentais com danos impostos, acesso aberto CC BY 4.0 no registro consultado); Z24 (monitoramento ambiental e dano progressivo, sujeito a solicitação e termos); NTNU (monitoramento de pontes, mas sem assumir rótulos de dano).
- **Plano de auditoria pendente:** triar todos os registros dos catálogos NEES/post-NEES; aprofundar os candidatos SHM de pontes; verificar acesso/licença/formatos/labels; revisar os artigos e baselines associados; escolher tarefa/base principal apenas após esses portões.
- Aplicação brasileira é fase condicional a parceria, autorização, dados e metadados adequados. Python e estatística integram o método; geoespacial é componente de caracterização de cobertura/proveniência se viável, não uma segunda pergunta.
- Requisito confirmado: execução **puramente remota**. Excluir visitas, instrumentação, coleta presencial e novos ensaios físicos; usar dados existentes em formato digital e colaboração/revisão especializada a distância. Dados brasileiros só entram se forem acessíveis remotamente e autorizados.
- Prazo constante do edital local: inscrições até **22/11/2026**. Planejamento deve reservar tempo para confirmação com orientador, revisão bibliográfica e revisão formal/anônima do plano.
