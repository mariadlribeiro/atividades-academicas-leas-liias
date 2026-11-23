# LIAA e LEAS · Acompanhamento do professor (08/09 a 06/11/2026)

**Fonte:** página do projeto no site da disciplina, mantida pelo professor:
https://unipampa4all.github.io/disciplinas/liaa/20262/projetos_html/maria-lurdes-incendio.html
(versão consultada em 23/11/2026; último commit do site em 20/11/2026).

A própria página avisa que é uma leitura assistida por IA, feita a partir das transcrições automáticas das aulas, e que deve ser revisada pelo professor. Abaixo está um resumo; o texto completo está no link.

- **Professor:** Prof. Dr. Diego Kreutz, com contribuições do Prof. Welfer (conforme a proposta de 20/10).
- **Grafia do nome:** a página escreve "Maria Eduarda (Duda)"; o nome usado nos trabalhos é Maria Heduarda Silva Cardoso.

## O que foi combinado em cada encontro

| Data | Disciplina | Tema | Combinado |
|---|---|---|---|
| 08/09 | LIAA | Proposta: aplicativo de detecção de incêndio por foto, com modelos já treinados (95–98% de acurácia) | Apresentar a análise do dataset (origem, características técnicas e rotulação), **sem treinamento nem modelos**. Fechar o escopo. |
| 18/09 | LIAA (atendimento) | Origem dos datasets; dúvida sobre a Atividade 3 da LEAS | Conferir à mão cerca de 5% de cada classe e remover imagens borradas ou fora de contexto. **LEAS:** trocar o artefato de cibersegurança por uma ferramenta, feita com IA, que valide o dataset; apresentar o mesmo trabalho nas duas disciplinas. |
| 22/09 | LIAA | Validação técnica dos três datasets (~3.559 imagens): integridade, duplicatas, vazamento | Explicar como as duplicatas foram detectadas (hash), analisar o balanceamento e mostrar exemplos de erros da IA ao classificar. |
| 02/10 | LIAA + LEAS | Duplicatas espelhadas, balanceamento (3.259 imagens), ResNet18/DenseNet121/3ª rede: acurácia 87,29% → 87,53% | **LIAA:** tabelas e gráficos comparando os cenários (original, limpo, segmentação, aumento, tudo). **LEAS:** benchmark parametrizável, gerado com IA, em repositório documentado. A Maria Heduarda passa a apresentar junto. |
| 16/10 | LIAA + LEAS | Revisão do dataset com o professor: classe "sem fogo" com flores e cachorros; só 70% revisado | **Um único dataset**, revisado por inteiro, em com fogo / sem fogo por ambiente (idealmente mais de mil por ambiente); repositório só com o dataset e a validação; apresentar só o dataset, sem treino. "80% do trabalho é no dataset." |
| 20/10 | LIAA | Sem apresentação | O professor enviou a proposta de dataset ([resumo](LIAA_proposta_do_professor_20-10.md)). São sugestões, não decisões. |
| 06/11 | LIAA + LEAS | Um só dataset; página de revisão feita com IA; 415 imagens revisadas; auditoria cega de 60; rótulos errados, sintéticas e quase duplicatas | Estudar como iluminação, ângulo e imagens parecidas afetam o treino; equilibrar e aumentar por classe e ambiente (**mínimo de mil por classe e por ambiente**) com imagens de outros datasets. Slides com menos teoria, mais detalhe técnico e a versão exata do modelo. **LEAS:** apresentar os resultados da avaliação com múltiplas LLMs, não só o link do Git. |

## Avaliação registrada na página (até 06/11)

Progresso 3/5 · Mérito 3/5 · Site 0/5 · Qualidade do site 0/5 · Vídeos 0/5. Na época ainda não havia site nem vídeo; os dois foram publicados depois (17 e 18/11).

## Pendências combinadas e como estão agora

A situação "agora" é a nossa leitura dos repositórios em 23/11/2026, não uma avaliação do professor.

| Pendência (06/11) | Situação em 23/11 | Onde ver |
|---|---|---|
| Estudar o efeito de iluminação, ângulo e imagens parecidas | **Parcial.** Medidas de luz, tamanho, formato, nitidez e cor (etapa 9); teste de atalho (etapa 13). Falta o estudo com especialistas e com casos difíceis. | [LIAA/01](../LIAA/01_dataset_ignis_alert.md), [LIAA/02](../LIAA/02_treino_e_teste_de_atalho.md) |
| Evitar quase duplicatas divididas entre treino e teste | **Feito.** Divisão por grupo de duplicatas (SHA-256 + dHash ≤ 6). | etapa 4 |
| Equilibrar e aumentar por classe e por ambiente (mín. 1.000) | **Parcial.** Floresta empatada em 510 × 510 com a segunda fonte; **abaixo do mínimo de mil**; cenas urbanas sem fogo ainda poucas. | etapa 10 |
| Concluir a revisão e corrigir rótulos errados | **Parcial.** Fonte 1 revisada por pessoas; os 400 da segunda fonte foram rotulados por IA às cegas e conferidos por amostra. | etapa 5 e 10 |
| Explicar os limiares de similaridade | **Feito no código e no site** (dHash, distância ≤ 6, página de pares). Conferir se foi explicado em aula. | etapa 3 |
| Slides com mais detalhe técnico e a versão exata do modelo | **Feito em 21/11** (slides técnicos). Conferir se a versão do modelo de IA aparece nos slides. | [LIAA/04](../LIAA/04_apresentacao_final.md) |
| Repositório só com o dataset e a validação | **Feito.** `dataset_ignis_alert`. | link no README |
| LEAS: apresentar a avaliação com múltiplas LLMs | **Pendente.** T7 entregue; T8 em andamento; vídeo com a diferença entre as LLMs combinado em 21/11. | [LEAS/02](../LEAS/02_tarefa_8.md) |
