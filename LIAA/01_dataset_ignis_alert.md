# LIAA · Dataset do Ignis Alert

| Campo | Registro |
|---|---|
| Disciplina | LIAA (Laboratório de Inteligência Artificial) |
| Atividade | Construção, revisão e equilíbrio do dataset Fogo / Sem Fogo |
| Professor | A confirmar |
| Período | Até 13/11/2026 (etapas 1 a 10); etapa 11 em 18/11/2026 |
| Situação | **Concluída** |
| Repositório | https://github.com/mariadlribeiro/dataset_ignis_alert |
| Site | https://mariadlribeiro.github.io/dataset_ignis_alert/ |

## Objetivo

Montar um dataset confiável para classificar imagens em **Fogo** e **Sem Fogo**, sem vazamento entre treino, validação e teste, e com cada decisão registrada.

## Regras definidas pela dupla

1. Nunca modificar, mover, renomear ou excluir os originais; trabalhar sempre em cópia.
2. Não excluir imagens automaticamente; o que fica de fora vai para uma lista com o motivo.
3. Não classificar pelo nome da pasta.
4. Fumaça não é fogo confirmado. **Fogo = chamas visíveis.**
5. Uma imagem ou grupo de duplicatas nunca fica em mais de um conjunto (treino, validação, teste).
6. Antes da organização definitiva, apresentar o plano e esperar aprovação.

## Etapas (cada uma é um script no repositório)

| Etapa | Script(s) | O que faz |
|---|---|---|
| 1. Origem | `01_origem.py` | Inventário e manifesto SHA-256 dos originais |
| 2. Validação | `02_validacao.py` | Arquivos corrompidos, formatos e tamanhos |
| 3. Duplicatas | `03_duplicatas.py`, `04b_pagina_pares.py` | Exatas (SHA-256) e quase iguais (dHash, distância ≤ 6) |
| 4. Divisão | `04_divisao.py` | Treino/validação/teste por grupo, nunca por imagem |
| 5. Revisão | `05a`–`05d` | Sugestões do CLIP; decisão final humana, exportada em CSV; auditoria cega |
| 6. Plano | `06_plano.py` | Plano da organização, aprovado antes de copiar |
| 7. Cópia | `07_organizar.py` | Cópia conferida por SHA-256 |
| 8. Equilíbrio | `08_equilibrio.py` | Pesos do sorteio (WeightedRandomSampler) |
| 9. Condições | `09a`–`09e` | Medidas de luz, tamanho, formato, nitidez, cor e moldura; revisão de 14 perguntas por imagem |
| 10. Segunda fonte | `10a`–`10d` | Inventário, sugestões, seleção por diversidade (k-centros) e integração |
| 11. Exportar | `11_exportar_treino.py` | Pastas `train/val/test` × `Fire/NoFire` para o treino |

## Resultado (confirmado nos relatórios do repositório)

- **1.388 imagens**: 751 com fogo e 637 sem fogo.
- Divisão: **971 treino, 210 validação, 207 teste**, por grupo de duplicatas.
- Fontes (Kaggle): `phylake1337/fire-dataset` (999 arquivos) e `cristiancristancho/forest-fire-image-dataset` (11.034 arquivos, dos quais **400** entraram, escolhidos por k-centros entre os sugeridos como floresta sem fogo e revisados).
- Floresta empatada: **510 com fogo e 510 sem fogo**.
- Pesos do sorteio: com fogo passou de 54,1% para 50%; sem fogo, de 45,9% para 50%. Validação e teste mantêm a distribuição real.
- Ainda há poucas cenas urbanas sem fogo no treino (3 casas, 4 prédios, 13 cenas de cidade). Peso não cria exemplos.

## Achado principal

Igualar a quantidade não igualou as condições: **49% das imagens sem fogo são quadradas, contra 1% das com fogo**; metade das sem fogo é pequena; as com fogo são mais escuras. Isso é um risco de atalho (shortcut learning), testado na etapa 13.

## Páginas de revisão criadas (HTML, abrem no navegador)

- `relatorios/04_divisao/pares.html`: pares parecidos (mesma cena ou não).
- `relatorios/05_sugestoes/revisao.html` e `revisao_ambiente.html`: fogo, fumaça, ambiente; auditoria cega.
- `relatorios/09_condicoes/revisao_condicoes.html`: 14 perguntas de condição por imagem.
- `relatorios/10_nova_fonte/.../selecao_A/revisao_floresta_A.html`: floresta da segunda fonte.
- `relatorios/13_atalho/revisao_atalho.html`: teste de atalho.

## Uso de IA

O código dos scripts e das páginas de revisão foi gerado com o Claude (Anthropic) e executado e conferido pelas autoras. O CLIP foi usado só para sugerir rótulos; a decisão final das imagens da fonte 1 foi humana. Os 400 rótulos da segunda fonte foram dados por IA às cegas e conferidos por amostra (limitação registrada).

## Pendências

- Conferência humana completa dos 400 rótulos da segunda fonte.
- Confirmar a licença da segunda fonte.
- Mais imagens urbanas sem fogo.
