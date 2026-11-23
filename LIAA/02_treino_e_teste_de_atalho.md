# LIAA · Treino das redes e teste de atalho

| Campo | Registro |
|---|---|
| Disciplina | LIAA |
| Atividade | Etapas 12 (treino) e 13 (teste de atalho) |
| Data | 18 e 19/11/2026 |
| Situação | **Concluída** |
| Scripts | `scripts/12_treinar.py`, `13a_selecao_atalho.py`, `13b_avaliar_atalho.py` |

## Protocolo

- Redes: **ResNet18, DenseNet121, EfficientNet-B0**, pré-treinadas no ImageNet.
- Aumento de dados só no treino; perda com peso por classe.
- Melhor época e limiar escolhidos pelo **F2 na validação** (num alerta, perder um incêndio custa mais que um alarme falso).
- Teste de 207 imagens usado **uma única vez**, no fim.
- Treinos rodados pelas autoras na CPU do próprio computador.

## Resultados no teste (207 imagens)

| Rede | F2 | Fogo perdido | Alarme falso |
|---|---|---|---|
| DenseNet121 | 99,1% | 1 | 1 |
| EfficientNet-B0 | 99,1% | 1 | 1 |
| ResNet18 | 97,8% | 3 | 0 |

## Teste de atalho (etapa 13)

297 fotos novas da segunda fonte, todas de floresta, **quadradas e pequenas** (148 com fogo, 149 sem), sem quase-duplicatas do dataset. É o formato que, no treino, quase só aparecia sem fogo. Mesmo limiar da validação.

| Rede | Recall de fogo no teste principal | Recall nas 297 fotos |
|---|---|---|
| ResNet18 | 97,3% | 95,3% |
| EfficientNet-B0 | 99,1% | 96,6% |
| DenseNet121 | 99,1% | 100% (297/297) |

Maior queda: 2,5 pontos. **Não há sinal de que as redes usem o formato no lugar da chama.** Limite: são casos claros, rotulados às cegas por IA e conferidos por amostra.

## Análise de erros

- Fogo que nenhuma rede achou: muita fumaça e chama pequena junto ao chão.
- Alarme falso da EfficientNet-B0: neblina num vale, parecida com fumaça.
- ResNet18 perdeu um fogo evidente por pouco (53% contra limiar de 58,5%): erro de limiar.
- Alarme falso da DenseNet121: árvore de outono alaranjada.

## Decisão

**EfficientNet-B0 vai para o aplicativo**: mesmo F2 da DenseNet121 e cerca de 3 vezes mais rápida (35 ms contra ~97 ms por imagem na CPU, campanha `custo` do benchmark). A DenseNet121 fica como referência de robustez.

## Primeira fase (apresentada em 02/10, segundo a página do professor)

3.259 imagens de três datasets (2.281 treino, 489 validação, 489 teste). ResNet18, DenseNet121 e uma terceira arquitetura, sem e com segmentação e aumento de dados: a limpeza mudou a acurácia de **87,29% para 87,53%**. O professor pediu tabelas comparando os cenários (original, limpo, segmentação, aumento, tudo) e, depois, recomeçar pelo dataset.

## Experimentos anteriores (registrados no documento inicial, a conferir)

O documento inicial (ChatGPT) registra experimentos feitos antes, no repositório `rd_ignisalert`:

| Grupo | Descrição |
|---|---|
| E01–E03 | Sem aumento de dados |
| E04–E06 | Aumento com torchvision |
| E07–E09 | Aumento com Augmentor |
| S05 | DenseNet121 + SLIC-100 + Augmentor |
| S06 | EfficientNet-B0 + SLIC-100 + Augmentor |

Resultado registrado do S05: F2 0,99335; precisão para fogo 0,98175; recall 0,99630; FP 5; FN 1; PR AUC 0,99931; limiar 0,2788004577. **Esses valores vieram do histórico e precisam ser conferidos nos arquivos de métricas antes de uma entrega formal.** Esses experimentos usavam outra divisão de dados, então não são diretamente comparáveis com os da etapa 12.
