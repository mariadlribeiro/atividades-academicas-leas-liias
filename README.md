# Atividades acadêmicas: LEAS e LIAA (2026/2)

Registro das atividades, projetos, decisões e entregas de duas disciplinas da UNIPAMPA, campus Alegrete, no semestre 2026/2.

- **LEAS:** Laboratório de Engenharia de Artefatos de Software.
- **LIAA:** Laboratório de Inteligência Artificial. No documento inicial, gerado com o ChatGPT, a sigla aparece como "LIIAS". Nos materiais do projeto (site, slides, README do benchmark), a sigla usada é LIAA. **Confirmar com o enunciado oficial qual é a sigla correta.**

Autoras dos trabalhos em dupla: **Maria de Lurdes Ribeiro da Rosa** e **Maria Heduarda Silva Cardoso**. Professor: **Prof. Dr. Diego Kreutz**.

Acompanhamento do projeto pelo professor: https://unipampa4all.github.io/disciplinas/liaa/20262/projetos_html/maria-lurdes-incendio.html ([resumo e situação das pendências](enunciados/LIAA_LEAS_acompanhamento_do_professor.md)).

## Como este repositório está organizado

| Pasta / arquivo | Conteúdo |
|---|---|
| [`HISTORICO_ACADEMICO.md`](HISTORICO_ACADEMICO.md) | O histórico completo, atualizado. Parte da versão inicial feita com o ChatGPT e acrescenta tudo o que foi feito depois. |
| [`LINHA_DO_TEMPO.md`](LINHA_DO_TEMPO.md) | O semestre em ordem de datas, com as próximas entregas. |
| [`LIAA/`](LIAA/) | Projeto Ignis Alert: dataset, treino das redes, teste de atalho, apresentação final e vídeos. |
| [`LEAS/`](LEAS/) | Tarefa 7, Tarefa 8 (avaliação de artefatos com LLMs) e o benchmark parametrizável. |
| [`atividades/`](atividades/) | Atividades novas ou transversais, como a apresentação de dicas de uso de IA. |
| [`enunciados/`](enunciados/) | Enunciados das tarefas, o acompanhamento do professor e a proposta de dataset de 20/10, com a comparação com o que foi feito. |
| [`materiais/`](materiais/) | Falas da apresentação final em PDF e a legenda da gravação. |
| [`INSTRUCOES_PARA_IA.md`](INSTRUCOES_PARA_IA.md) | As regras de trabalho da dupla, para anexar a qualquer conversa nova com uma IA. |
| [`GLOSSARIO.md`](GLOSSARIO.md) | Termos técnicos explicados em uma linha (F2, dHash, k-centros, atalho, selos D/F/S/R...). |
| [`prompts/`](prompts/) | Os prompts de continuidade do documento inicial. |
| [`documentos/`](documentos/) | O documento original em Word (versão inicial, gerada com o ChatGPT), sem alterações. |

## Para começar uma conversa nova com uma IA

Anexe `HISTORICO_ACADEMICO.md` e `INSTRUCOES_PARA_IA.md` (ou cole o link deste repositório) e use o Prompt 1 de [`prompts/PROMPTS.md`](prompts/PROMPTS.md).

## Situação das atividades

| Disciplina | Atividade | Situação | Registro |
|---|---|---|---|
| LIAA | Dataset do Ignis Alert (13 etapas, 1.388 imagens) | Concluída | [LIAA/01_dataset_ignis_alert.md](LIAA/01_dataset_ignis_alert.md) |
| LIAA | Treino de 3 redes e teste de atalho | Concluída | [LIAA/02_treino_e_teste_de_atalho.md](LIAA/02_treino_e_teste_de_atalho.md) |
| LIAA | Vídeos (retrospectiva de 2 min e curta em estilo LEGO) | Retrospectiva no site; curta LEGO a confirmar | [LIAA/03_videos.md](LIAA/03_videos.md) |
| LIAA + LEAS | Apresentação final (21/11/2026) | Apresentada; gravação legendada | [LIAA/04_apresentacao_final.md](LIAA/04_apresentacao_final.md) |
| LEAS | Tarefa 7: LLMs reproduzem os selos de um artefato? | Entregue (set. 2026) | [LEAS/01_tarefa_7.md](LEAS/01_tarefa_7.md) |
| LEAS | Tarefa 8: robustez das avaliações da T7 | Em andamento (23/11/2026) | [LEAS/02_tarefa_8.md](LEAS/02_tarefa_8.md) |
| LEAS | Benchmark parametrizável do Ignis Alert | Concluído (19/11/2026) | [LEAS/03_benchmark.md](LEAS/03_benchmark.md) |
| — | Apresentação: dicas práticas de uso de IA e agentes | **A fazer** | [atividades/apresentacao_dicas_ia.md](atividades/apresentacao_dicas_ia.md) |

## Repositórios relacionados

| Repositório | O que tem |
|---|---|
| [dataset_ignis_alert](https://github.com/mariadlribeiro/dataset_ignis_alert) | Pipeline do dataset, treino, teste de atalho, benchmark e site do projeto |
| [Site do projeto](https://mariadlribeiro.github.io/dataset_ignis_alert/) | Resumo público, com o vídeo de 2 minutos |
| [rd_ignisalert](https://github.com/mariadlribeiro/rd_ignisalert) | Experimentos anteriores de treino (E01–E09, SLIC, Grad-CAM) |
| [mariadlribeiro.github.io](https://github.com/mariadlribeiro/mariadlribeiro.github.io) | Site pessoal; `/dataset/` redireciona para o site do projeto |
| artefatos-atividade-7 | Tarefas 7 e 8 da LEAS (repositório privado) |

## Regra deste histórico

Cada registro separa o que foi **confirmado** (há arquivo, commit ou relatório) do que ainda **precisa ser conferido**. Nada é marcado como concluído sem confirmação.
