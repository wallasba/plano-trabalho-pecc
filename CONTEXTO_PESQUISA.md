# Contexto da pesquisa — PECC

## Objetivo

Preparar uma proposta de trabalho e pesquisa para candidatura ao doutorado no PECC, com orientação principal em Computação ou coorientação na área. O interesse é construir uma base forte em computação, inteligência artificial — incluindo IA generativa — e estatística, aplicadas a problemas de inspeção e monitoramento de pontes/obras de arte especiais (OAEs). A pesquisa deve priorizar dados abertos e públicos e ser compatível com execução remota.

## Direção de pesquisa em discussão

Recorte promissor: métodos robustos e estatisticamente avaliados de visão computacional multimodal para identificar e caracterizar danos em imagens de inspeção de pontes, usando modelos pré-treinados (por exemplo, modelos de visão e linguagem) e saídas estruturadas vinculadas às evidências visuais.

A contribuição de doutorado deve ir além de comparar modelos prontos. Pode investigar generalização entre conjuntos de dados/domínios, dados escassos e desbalanceados, calibração e quantificação de incerteza, e avaliar se adaptação eficiente ou aumento sintético de dados melhora o desempenho em dados reais. IA generativa não deve produzir relatórios livres sem validação e sem referências às evidências.

A análise estatística pode incluir partições de treino/teste por ponte para evitar vazamento, validação cruzada entre bases, intervalos de confiança, comparação de modelos, análise por classe e domínio, calibração e métodos de incerteza. As técnicas finais dependem da pergunta de pesquisa e devem ser acordadas com os orientadores.

## Dados e repositórios para investigar

- [DataCenterHub / legado NEES](https://datacenterhub.org/nees.html): repositório histórico com dados de ensaios estruturais, terremotos, pontes e monitoramento. A disponibilidade, licença, formato e metadados precisam ser conferidos conjunto a conjunto; alguns dados podem estar em arquivos compactados ou indisponíveis em repositórios sucessores.
- [NTNU — dados abertos de monitoramento estrutural](https://www.ntnu.edu/kt/open-data): séries de sensores de pontes como Hardanger, Bergsøysund, Gjemnessund e Hell; é mais apropriado para SHM e sinais do que para visão computacional de danos.
- [DesignSafe / NHERI Data Depot](https://www.designsafe-ci.org/): dados de engenharia de riscos naturais e ensaios experimentais, potencial fonte complementar.
- [Hell Bridge Test Arena — Zenodo](https://zenodo.org/records/14632942): respostas dinâmicas sob estados de referência e danos impostos.
- [dacl10k](https://openaccess.thecvf.com/content/WACV2024/papers/Flotzinger_dacl10k_Benchmark_for_Semantic_Bridge_Damage_Segmentation_WACV_2024_paper.pdf) e [Cambridge Bridge Inspection Dataset](https://www.repository.cam.ac.uk/items/f73994b0-b86f-4007-b0b0-cd0179c6f865): candidatos para inspeção visual anotada.

Não presumir que dados de sensores e imagens possam ser vinculados entre si. Rótulos de dano em imagens não equivalem a relatórios narrativos; geração de descrições técnicas precisaria de referências textuais adequadas e revisão por especialistas.

## Viabilidade, limites e recursos

A pesquisa é factível como trabalho computacional remoto, desde que o escopo fique delimitado, as licenças permitam o uso e exista acesso a GPU (universitária, compartilhada ou nuvem), armazenamento e orientação adequada em Computação e engenharia estrutural. Modelos pré-treinados e adaptação eficiente podem evitar treinamento de fundações do zero. Revisão especializada de uma amostra será necessária para afirmações técnicas sobre danos.

Sem conjunto público brasileiro representativo e licenciado para teste, os resultados devem ser apresentados como avaliação metodológica em bases internacionais, sem alegar validação para OAEs brasileiras. Um ramo de séries de sensores pode ser estudo complementar, mas combinar desde o início imagens, geração de relatórios, SHM, previsão de deterioração e validação nacional tende a tornar a tese ampla demais.

## Requisitos da proposta PECC

Conforme o edital PECC 01/2026 consultado na conversa, o plano tem limite de 10 páginas e requer Introdução, Justificativa, Objetivos, Revisão da Literatura, Metodologia e Referências. A avaliação enfatiza contextualização/relevância/atualidade bibliográfica, metodologia e aderência às linhas do programa. Confirmar os requisitos no edital vigente antes da submissão.

## Próximos passos

1. Confirmar com possíveis orientadores a linha do PECC e a adequação do recorte à Computação.
2. Fazer inventário reproduzível de 2–4 bases candidatas: arquivos disponíveis, licença, número e tipo de amostras, rótulos, unidade de agrupamento (ponte), metadados e restrições.
3. Escolher uma pergunta principal e critérios de avaliação após a auditoria dos dados.
4. Definir o desenho estatístico, os baselines, validação entre domínios e métricas antes dos experimentos.
5. Redigir a proposta conforme o edital vigente, com contribuições, limitações e cronograma compatíveis com doutorado.
