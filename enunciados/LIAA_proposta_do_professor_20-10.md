# LIAA · Proposta de dataset enviada pelo professor (20/10/2026)

**Fonte:** https://unipampa4all.github.io/disciplinas/liaa/20262/maria_de_lurdes_dataset.html
"Dataset de Incêndio Florestal — um dataset de incêndio florestal que dê para confiar". Orientação: Prof. Dr. Diego Kreutz, com contribuições do Prof. Welfer. Outubro de 2026.

O professor deixou claro que são **sugestões e direções para discutir, não decisões**. O texto completo (com catálogo de datasets, onde achar imagens e lista de artigos) está no link. Abaixo, os pontos principais e como o trabalho da dupla se compara a eles.

## Pontos principais da proposta

1. **Escopo:** um ambiente só — floresta e vegetação nativa, vista de longe (torre, morro, beira de estrada ou drone inclinado). Satélite, closes de chama e outros ambientes ficam de fora, ou só como pequeno teste de generalização.
2. **Classes:** `incendio` e `sem_incendio` (obrigatórias); `foco_local` e `incendio_extenso` (opcionais). **Pelo menos 30% do "sem incêndio" devem ser negativos difíceis:** neblina, nuvem baixa, pôr do sol, poeira, vapor, chaminé.
3. **Fumaça conta como incêndio: sim.** Em floresta, a fumaça é o sinal mais comum e mais precoce.
4. **Sete passos de curadoria:** guia de rotulagem antes de rotular; olhar 100% das imagens; remover duplicatas e quase duplicatas (pHash, embeddings); dividir por grupo; medir concordância entre anotadores (kappa de Cohen em 200–300 imagens, meta ≥ 0,8); caçar erros de rótulo com o modelo (cleanlab); ficha do dataset com `metadados.csv`.
5. **Três experimentos:** A) bruto × curado; B) divisão aleatória × por grupo; C) generalização (imagens brasileiras e, se der, estrada/cidade).
6. **Métricas:** precisão, recall e F1 por classe, matriz de confusão e taxa de falso alarme nos negativos difíceis.
7. **Cronograma de cerca de 12 semanas**, com versão mínima se o tempo apertar.

## Comparação com o que a dupla fez

Leitura nossa, em 23/11/2026, para orientar os próximos passos. Não é avaliação do professor.

| Ponto da proposta | O que a dupla fez | Situação |
|---|---|---|
| Escopo só floresta | Dataset com vários ambientes; a floresta foi equilibrada (510 × 510) e o teste de atalho usou só floresta | Parcial |
| **Fumaça conta como incêndio** | Regra da dupla: **fogo = chama visível; fumaça sozinha não é fogo** | **Diferente da proposta.** Decidir com o professor e justificar a escolha. |
| 30% de negativos difíceis | Não medido. Neblina, pôr do sol e folhas de outono apareceram como erros das redes | A fazer |
| Guia de rotulagem escrito | Regras curtas no README; sem guia com exemplos por classe | Parcial |
| Olhar 100% das imagens | Fonte 1 revisada por pessoas; 400 da fonte 2 rotuladas por IA às cegas e conferidas por amostra | Parcial |
| Duplicatas e quase duplicatas | SHA-256 + dHash (≤ 6), página de pares, grupos | Feito |
| Divisão por grupo | Grupos de duplicatas inteiros num só conjunto | Feito |
| Kappa entre anotadores | Auditoria cega humano × IA (60 imagens em 06/11); sem kappa entre duas pessoas | A fazer |
| cleanlab | Não usado; análise de erros feita à mão nos erros das redes | A fazer |
| Ficha do dataset / metadados.csv | Inventário e CSVs por etapa; README com etapas | Parcial (falta licença por fonte e uma ficha única) |
| Experimento A (bruto × curado) | Não feito como experimento separado | A fazer |
| Experimento B (aleatória × por grupo) | Não feito como experimento separado | A fazer |
| Experimento C (generalização) | Teste de atalho com 297 fotos de outra fonte (parecido, mas não igual) | Parcial |
| Métricas | F2, recall, fogo perdido e alarme falso; matriz por condição | Feito (com F2 no lugar de F1) |
