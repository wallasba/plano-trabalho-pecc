# Análise preliminar de viabilidade — doutorado PECC 2027

Data da análise: 5 de novembro de 2026. Esta nota fundamenta a escolha do tema e preserva as decisões para retomada. É uma análise documental; os arquivos completos das bases ainda não foram baixados nem auditados.

## 1. Decisão de pesquisa

**Recomendação:** investigar a confiabilidade de modelos de visão computacional para reconhecer e localizar danos em imagens de inspeção de pontes quando mudam a ponte, a origem dos dados ou as condições de aquisição. A pergunta central proposta é: **como detectar quando um modelo de danos visuais deixa de ser confiável fora do domínio em que foi treinado, e como reduzir esse erro com adaptação eficiente e avaliação estatística?**

A contribuição doutoral potencial é um protocolo reproduzível de avaliação entre bases, acompanhado de um método de calibração, detecção de mudança de domínio ou adaptação eficiente que demonstre melhora estatisticamente sustentada em dados externos. O método ainda precisa ser definido após auditoria dos rótulos e metadados. Publicar somente uma comparação de modelos prontos seria insuficiente. Uma aplicação de PLN ou IA agêntica pode ser estudo posterior, desde que haja textos de referência, hipótese mensurável e revisão técnica; não integra a pergunta principal.

**Juízo preliminar:** alto potencial de relevância científica e aplicação em inspeções, com dificuldade **média a alta** e viabilidade **condicional**. A originalidade e o impacto não estão garantidos pelo tema. Exigem revisão atualizada, acesso aos dados, um problema de generalização demonstrável e resultado superior a baselines fortes. A disponibilidade de identificadores de ponte e a compatibilidade de rótulos entre bases são os principais pontos de decisão.

## 2. Exigências do edital e aderência

O PDF local, apesar do nome de arquivo com 2026, identifica-se internamente como **Edital nº 01/2027** para ingresso no primeiro período de 2027. Inscrições: **26/10 a 22/11/2026, até 23h59** (itens 4.1 e 8.1). Para o doutorado, exige plano de trabalho e pesquisa, diplomas, históricos, Lattes com comprovantes, documentos pessoais e proficiência de leitura/compreensão em inglês (item 4.6.2).

| Exigência | Situação do recorte | Ação necessária |
|---|---|---|
| Introdução, Justificativa, Objetivos, Revisão da Literatura, Metodologia e Referências | Há direção registrada, mas ainda não há plano submetível | Redigir essas seis partes com pergunta e hipótese explícitas |
| Até 10 páginas, A4, espaço 1,5, Times New Roman 12; capa com nome, título e linha; demais páginas anônimas | Ainda não formatado | Aplicar formato e revisar anonimização (itens 5.2.3–5.2.4) |
| Relevância, contexto e bibliografia atual: 4 pontos | Potencial alto, ainda sem revisão crítica suficiente | Mostrar lacuna específica e trabalhos recentes, inclusive baselines competitivos |
| Metodologia: 3 pontos | Desenho estatístico delineado, não fechado | Definir dados, partições, métricas, comparações, incerteza e contingências |
| Aderência às linhas do PECC: 3 pontos | Aplicação em pontes é pertinente; enquadramento formal pendente | Confirmar linha e orientação; formular a contribuição como problema de inspeção/engenharia estrutural |

O plano é **eliminatório, com nota mínima 7,0** (item 6.4). O Anexo A.2.1 distribui 4/3/3 pontos aos três critérios. A fórmula de classificação final do item 7.1.2 usa histórico e currículo, 50% cada, depois da etapa eliminatória do plano; portanto, boa proposta não substitui a documentação e a pontuação curricular. A seleção permite inscrição em apenas uma área de concentração (item 2.1.7). A área de **Estruturas** parece o enquadramento inicial mais natural, sujeito à confirmação da linha de pesquisa e de orientador. Resultados anteriores do PECC mencionam “Métodos Numéricos e Computacionais Aplicados à Engenharia (Estruturas)” e “Identificação de Sistemas e Controle Estrutural”, mas isso não confirma, por si só, a oferta atual de orientação.

Fonte local: `referencias/Edital_PECC_01_2026_05_0_2026_R06_assinado.pdf`. Exemplo oficial de linhas usadas em seleção anterior: https://peccft.unb.br/images/2025/Resultado_Final_-_Doutorado_-_05-03-25.pdf

## 3. Bases públicas: evidência e lacunas

| Base | Evidência confirmada em fonte primária | Papel possível | Ponto a verificar nos arquivos |
|---|---|---|---|
| [dacl10k](https://github.com/phiyodr/dacl10k-toolkit) | 9.920 imagens de inspeção, anotações por polígonos e 19 classes na versão do desafio; toolkit indica licença CC BY-NC 4.0 e fornece downloads e hashes | Treino e avaliação principal de localização de danos | Identificadores de ponte/origem, distribuição por classe, splits e termos exatos de redistribuição |
| [dacl1k](https://www.sciencedirect.com/science/article/pii/S0952197624012648) e [toolkit](https://github.com/phiyodr/building-inspection-toolkit) | 1.474 imagens; tarefa de classificação multirrótulo, descrita como teste em condições reais | Avaliação externa para rótulos compatíveis em nível de imagem | Licença, disponibilidade efetiva, correspondência de classes e sobreposição com dacl10k |
| [CODEBRIM](https://zenodo.org/records/2620293) | Imagens originais com caixas e versões recortadas/classificação; quatro arquivos de dados somam 36,4 GB, com versões alternativas do mesmo conjunto | Avaliação externa complementar | Licença no arquivo `license.md`, identidade das pontes e duplicatas entre versões |
| [Cambridge Bridge Inspection Dataset](https://www.repository.cam.ac.uk/items/f73994b0-b86f-4007-b0b0-cd0179c6f865/full) | ZIP público de 27,63 MB, CC BY 4.0 | Piloto ou teste externo pequeno | Rótulos, quantidade efetiva, identificadores e adequação à pergunta |
| [NEES / DataCenterHub](https://datacenterhub.org/resources/257) | Problemas de referência em controle e SHM, com documentação e arquivos MATLAB/simulação conforme o registro | Rota alternativa em sinais/modelagem | Link antigo do usuário retornou 404 no acesso web; conferir downloads individuais, licença e relevância para pontes |
| [Hell Bridge Test Arena](https://zenodo.org/records/14632942) | Ponte de aço experimental, estados de dano impostos, aceleração/deformação, arquivo HDF5 de 2,5 GB a 100 Hz | Rota alternativa de detecção de dano em sinais | Generalização além da ponte experimental e licença específica |
| [NTNU](https://www.ntnu.edu/kt/open-data) | Portal lista Hardanger, Bergsøysund, Gjemnessund e Hell; [Bergsøysund](https://zenodo.org/records/8051201) inclui arquivos HDF5 de 8,2 e 39,3 GB | Rota alternativa em séries de sensores | Estados de dano rotulados; tamanho e custo de armazenamento variam muito |

**Limite importante:** imagens e sensores desses acervos não estão pareados por ponte. Não se deve propor fusão multimodal direta sem fonte que forneça alinhamento real. Da mesma forma, diferenças entre máscaras, caixas e rótulos de imagem exigem uma tarefa comum previamente definida; resultados entre tarefas distintas não são comparáveis diretamente.

## 4. Alternativas e escolha

| Rota | Potencial científico | Risco principal | Recurso computacional | Decisão |
|---|---|---|---|---|
| Confiabilidade de inspeção visual sob mudança de domínio | Alto se houver avanço metodológico e avaliação externa rigorosa | Metadados por ponte e rótulos incompatíveis | GPU útil; não exige treinar modelo fundacional do zero | **Prioritária, condicionada à auditoria** |
| Detecção de dano por séries de sensores | Alto para SHM, com vínculo claro a Estruturas | Estados de dano em poucas estruturas; efeito de ambiente e operação | CPU pode bastar para baselines; GPU para deep learning | Plano alternativo se a rota visual falhar |
| Plataforma integrada de visão, SHM, PLN e agentes | Potencial aplicado, mas contribuição causal difícil de isolar | Dados não pareados, validação especializada e escopo excessivo | Alto e variável | Não indicada como pergunta principal |

O problema central deve medir desempenho por classe e por domínio, calibração/incerteza, falhas em dados externos e custo de adaptação. Partições devem ser por ponte ou outra unidade de origem quando a identificação existir; se não existir, declarar a limitação e usar separação por fonte e busca de duplicatas. Intervalos de confiança devem respeitar a unidade independente disponível. Um especialista em pontes deve revisar uma amostra de erros relevantes para evitar interpretação estrutural indevida. Sem dados brasileiros representativos, a tese não poderá alegar validação para OAEs brasileiras.

## 5. Máquina e dificuldade

As faixas abaixo são **estimativas de planejamento, não requisitos oficiais nem tempos medidos**. Dependem da resolução, arquitetura, tamanho de lote e quantidade de repetições. O [PyTorch](https://docs.pytorch.org/get-started/locally/) oferece execução em CPU e plataformas com GPU; a instalação deve ser escolhida conforme o hardware disponível.

| Nível | Configuração indicativa | O que permite |
|---|---|---|
| Mínimo para auditoria e baselines leves | CPU moderna de 4–8 núcleos, 16 GB RAM, SSD com 100 GB livres; sem GPU dedicada | Inventário, estatística, modelos clássicos e inferência pequena; treinamento profundo será lento |
| Trabalho principal recomendado | CPU de 8 núcleos, 32 GB RAM, SSD de 1 TB, GPU com 12–16 GB de VRAM ou acesso equivalente em nuvem/universidade | Ajuste eficiente de modelos de visão, resolução controlada, repetição de experimentos e análise de erros |
| Experimentos amplos | 64 GB RAM, armazenamento acima de 1 TB e GPU de 24 GB ou serviço compartilhado | Modelos maiores, resolução elevada, buscas extensas e alguns modelos de visão e linguagem |

Não há justificativa inicial para comprar hardware de ponta. Antes da aquisição, executar um piloto curto com dados acessíveis, registrar pico de RAM/VRAM, tempo por época e volume de armazenamento, então dimensionar o restante. O CODEBRIM, por exemplo, distribui versões alternativas grandes; não é necessário guardar todas para um primeiro experimento. A rota Hell exige pelo menos espaço para o arquivo de 2,5 GB e intermediários; a série Bergsøysund completa é muito maior.

**Dificuldade estimada:** curadoria e licenças (média), harmonização e prevenção de vazamento (alta), baselines (média), inovação metodológica e prova de generalização (alta), interpretação estrutural (alta sem coorientação da área). O gargalo científico é a validade da avaliação, não apenas a potência da máquina.

## 6. Portões de viabilidade e próximos passos

1. Confirmar pelo menos uma base principal acessível, licença compatível e anotações reproduzíveis.
2. Verificar se existe unidade de agrupamento por ponte ou origem; documentar duplicatas e limites de independência.
3. Escolher uma tarefa comum com rótulos equivalentes em ao menos uma base externa. Se isso falhar, formular a contribuição com avaliação interna por domínio explicitamente delimitada, sem prometer validação entre bases.
4. Reproduzir um baseline leve e medir uso de recursos antes de fixar arquitetura e máquina.
5. Revisar bibliografia recente para localizar a lacuna concreta; pactuar a linha e a supervisão em Estruturas e Computação.
6. Redigir o plano de até 10 páginas com hipótese, contribuições, método, riscos e cronograma; revisar anonimização e documentos de inscrição antes de 22/11/2026.

Esta nota é deliberadamente **preliminar**: a elegibilidade dos conjuntos, a originalidade exata da contribuição e a configuração de GPU exigem auditoria de arquivos e revisão sistemática antes de se tornarem afirmações definitivas na proposta.
