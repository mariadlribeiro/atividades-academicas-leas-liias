# Histórico acadêmico: LEAS e LIAA

Registro de disciplinas, projetos, atividades e prompts de continuidade · UNIPAMPA Alegrete · 2026/2

**Versão 2 — 23/11/2026.** A versão 1 (novembro de 2026) foi gerada com o ChatGPT a partir do histórico disponível naquele momento e está em [`documentos/`](documentos/), sem alterações. Esta versão mantém o conteúdo dela e acrescenta o que foi feito depois, conferido nos repositórios.

> **Sigla.** A versão 1 chama a disciplina de IA de "LIIAS". Nos materiais do projeto (site, slides, benchmark) a sigla é **LIAA**. Confirmar no enunciado oficial.

## 1. Visão geral das disciplinas

| Disciplina | Foco | Trabalhos |
|---|---|---|
| **LEAS** — Laboratório de Engenharia de Artefatos de Software | Documentação, organização e avaliação de artefatos de software | Tarefas 7 e 8 (avaliação de artefato com LLMs); benchmark parametrizável do Ignis Alert |
| **LIAA** — Laboratório de Inteligência Artificial | Desenvolvimento, treino e avaliação de modelos de IA | Projeto Ignis Alert: dataset Fogo/Sem Fogo, treino de 3 redes, teste de atalho |

Dupla: Maria de Lurdes Ribeiro da Rosa e Maria Heduarda Silva Cardoso.

**Professor:** Prof. Dr. Diego Kreutz, com contribuições do Prof. Welfer, conforme a página da disciplina e a proposta de 20/10 ([acompanhamento](enunciados/LIAA_LEAS_acompanhamento_do_professor.md)). Nos materiais do vídeo LEGO, o Prof. Fábio Basso aparece como orientador da pesquisa; confirmar se é outro vínculo (por exemplo, TCC).

**Acompanhamento pelo professor:** https://unipampa4all.github.io/disciplinas/liaa/20262/projetos_html/maria-lurdes-incendio.html

## 2. LEAS

### 2.1 Registros da versão 1

- Estudo do artigo "Research Artifacts in Software Engineering Publications: Status and Trends", de Liu et al. (2024).
- Atividade relacionada à avaliação de artefatos de software.
- Tarefa 7 e Tarefa 8 — Avaliação de Artefatos de Software (a 8 continua a 7).
- Atividade 3 (artefato de cibersegurança), atrasada em 18/09: o professor sugeriu trocá-la por uma ferramenta de validação do dataset feita com IA; em 02/10 a sugestão virou o benchmark parametrizável.

### 2.2 Atualização

| Atividade | Situação | Detalhes |
|---|---|---|
| Tarefa 7 | Entregue (set. 2026) | [LEAS/01_tarefa_7.md](LEAS/01_tarefa_7.md) |
| Tarefa 8 | Em andamento (23/11/2026) | [LEAS/02_tarefa_8.md](LEAS/02_tarefa_8.md) |
| Benchmark parametrizável | Concluído (19/11/2026) | [LEAS/03_benchmark.md](LEAS/03_benchmark.md) |

Os enunciados completos das Tarefas 7 e 8 estão em [`enunciados/`](enunciados/).

### 2.3 Ainda a recuperar

- Critérios de avaliação, datas e prazos de cada tarefa.
- Comprovantes das entregas.

## 3. LIAA

### 3.1 Projeto Ignis Alert

Detecção preliminar de incêndios em imagens: classificar em **Fogo** e **Sem Fogo** para apoiar o monitoramento ambiental. Frase-guia do projeto: *a IA faz a triagem, quem responde decide.*

### 3.2 Conteúdos e técnicas (versão 1, todos usados no projeto)

Preparação, organização e auditoria de datasets; classificação binária; aumento de dados; redes convolucionais e transferência de aprendizado; segmentação com SLIC; Grad-CAM; treino, validação, teste e métricas; exportação do modelo para o aplicativo.

### 3.3 Atualização

| Atividade | Situação | Detalhes |
|---|---|---|
| Dataset (13 etapas, 1.388 imagens) | Concluído | [LIAA/01_dataset_ignis_alert.md](LIAA/01_dataset_ignis_alert.md) |
| Treino de ResNet18, DenseNet121 e EfficientNet-B0 + teste de atalho | Concluído | [LIAA/02_treino_e_teste_de_atalho.md](LIAA/02_treino_e_teste_de_atalho.md) |
| Vídeos (retrospectiva e curta LEGO) | Retrospectiva publicada; LEGO a confirmar | [LIAA/03_videos.md](LIAA/03_videos.md) |
| Apresentação final conjunta (21/11/2026) | Apresentada | [LIAA/04_apresentacao_final.md](LIAA/04_apresentacao_final.md) |

**Resumo dos resultados:** EfficientNet-B0 e DenseNet121 empataram no teste (F2 99,1%, 1 fogo perdido e 1 alarme falso cada); a EfficientNet-B0 foi escolhida para o aplicativo por ser cerca de 3 vezes mais rápida. No teste de atalho, a maior queda de recall foi de 2,5 pontos: sem sinal de que as redes usem o formato da foto no lugar da chama.

### 3.4 Primeira fase (08/09 a 16/10)

O projeto começou como um aplicativo de alerta com três redes já treinadas (95–98% de acurácia) em três datasets misturados. O professor reorientou para validar os dados antes de qualquer modelo. Até 02/10: 3.259 imagens (2.281 treino, 489 validação, 489 teste); ResNet18, DenseNet121 e uma terceira rede, com e sem segmentação e aumento de dados; a limpeza mudou a acurácia de 87,29% para 87,53%. Em 16/10 o professor pediu para recomeçar por um único dataset, revisado por inteiro e organizado por ambiente; em 20/10 enviou uma [proposta de dataset](enunciados/LIAA_proposta_do_professor_20-10.md). O trabalho atual (etapas 1 a 13) é a resposta a essa reorientação.

> **Ponto a decidir com o professor:** a proposta de 20/10 conta **fumaça como incêndio**; a regra da dupla é **fogo = chama visível**. A comparação completa está na [proposta](enunciados/LIAA_proposta_do_professor_20-10.md).

### 3.5 Experimentos anteriores (versão 1, a conferir)

E01–E03 sem aumento; E04–E06 com torchvision; E07–E09 com Augmentor; S05 DenseNet121 + SLIC-100 + Augmentor; S06 EfficientNet-B0 + SLIC-100 + Augmentor. Valores do S05 em [LIAA/02_treino_e_teste_de_atalho.md](LIAA/02_treino_e_teste_de_atalho.md). Conferir nos arquivos de métricas do `rd_ignisalert` antes de usar.

### 3.6 Questões metodológicas (versão 1, com o que foi decidido)

| Questão | Como ficou |
|---|---|
| Vazamento entre treino, validação e teste | Divisão por grupo de duplicatas (SHA-256 + dHash) |
| Escolha do limiar | Calibrado pelo F2 na validação; teste usado uma vez |
| Ordem das classes no ImageFolder | Pastas `Fire/NoFire` com `split_manifest.csv` |
| Erros com neblina, pôr do sol, iluminação, objetos alaranjados | Confirmados na análise de erros; viram o próximo teste com casos difíceis |

## 4. Outras atividades

| Atividade | Situação | Detalhes |
|---|---|---|
| Apresentação com dicas práticas de uso de IA e agentes | A fazer | [atividades/apresentacao_dicas_ia.md](atividades/apresentacao_dicas_ia.md) |

## 5. Como usar este histórico em novas conversas

Anexe este arquivo (ou o link do repositório) à nova conversa e use os prompts em [`prompts/PROMPTS.md`](prompts/PROMPTS.md). Depois de cada entrega, registre a atividade com os campos do Prompt 6 e atualize a tabela abaixo.

## 6. Controle de atualização

| Data | Disciplina | Atividade/alteração | Situação |
|---|---|---|---|
| 08/09/2026 | LIAA | Proposta inicial; professor pede análise do dataset antes de modelos | Reorientado |
| 18/09/2026 | LEAS | Atividade 3 trocada por ferramenta de validação do dataset | Reorientado |
| 28/09/2026 | LEAS | Tarefa 7 publicada no repositório | Entregue |
| 02/10/2026 | LIAA + LEAS | Comparação de redes (87,29% → 87,53%); sugestão do benchmark | Apresentado |
| 16/10/2026 | LIAA | Recomeçar por um único dataset, por ambiente | Reorientado |
| 20/10/2026 | LIAA | Proposta de dataset enviada pelo professor | Recebida |
| 06/11/2026 | LIAA + LEAS | Dataset único, página de revisão, auditoria cega de 60 imagens | Apresentado |
| 13/11/2026 | LIAA | Dataset: etapas 9 e 10 (condições e segunda fonte), 1.388 imagens | Concluído |
| 17/11/2026 | LIAA | Site do projeto no GitHub Pages | Publicado |
| 18/11/2026 | LIAA | Etapas 11 e 12: exportação e treino | Concluído |
| 18/11/2026 | LIAA | Curta em estilo LEGO | A confirmar |
| 19/11/2026 | LIAA | Etapa 13: teste de atalho | Concluído |
| 19/11/2026 | LEAS | Benchmark parametrizável, 6 campanhas executadas | Concluído |
| 21/11/2026 | LIAA + LEAS | Apresentação final; gravação legendada | Apresentada |
| 23/11/2026 | LEAS | Tarefa 8: protocolo, verificação do artefato, rodadas do Claude | Em andamento |
| 23/11/2026 | — | Apresentação de dicas de uso de IA: enunciado registrado | A fazer |
| 23/11/2026 | — | Histórico migrado para este repositório (versão 2) | Concluído |
| 23/11/2026 | — | Enunciados, materiais, instruções para IA, glossário e linha do tempo | Concluído |
| 23/11/2026 | LIAA + LEAS | Acompanhamento do professor e proposta de 20/10 registrados, com comparação | Concluído |

## 7. Observações

Este histórico apoia a continuidade do trabalho, mas não substitui os materiais oficiais das disciplinas. Itens marcados "a confirmar" ou "a conferir" não devem ir para uma entrega formal sem verificação.
