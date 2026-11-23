# LEAS · Benchmark parametrizável do Ignis Alert

| Campo | Registro |
|---|---|
| Disciplina | LEAS |
| Origem | Em 18/09, troca da Atividade 3 (cibersegurança) por uma ferramenta de validação feita com IA; em 02/10, sugestão do professor: transformar os experimentos num artefato de benchmark parametrizável, gerado com IA, em que o usuário escolhe a campanha |
| Data | 19/11/2026 |
| Situação | **Concluído** |
| Onde está | https://github.com/mariadlribeiro/dataset_ignis_alert/tree/main/benchmark |

## Como funciona

Cada **campanha** é um arquivo TOML: em `[base]` ficam os valores fixos e em `[grade]` as listas; o runner `benchmark/rodar.py` roda todas as combinações, mostra o plano e o tempo estimado (`--so-plano`) e não treina de novo uma rodada que já existe. Sai `tabela.csv`, `relatorio.md` e `grafico.png` por campanha.

## Campanhas executadas pelas autoras (19/11/2026)

| Campanha | Pergunta | Resultado |
|---|---|---|
| `rapida` | O ambiente está pronto? | Teste de fumaça |
| `redes` | Qual arquitetura? | F2 no teste de 97,8% (ResNet18) a 99,1% (DenseNet121 e EfficientNet-B0); validação saturada (99,5–99,8%) |
| `aumento` | Aumento de dados ajuda? | Diferença de uma imagem, menor que o acaso |
| `sementes` | Quanto muda por acaso? | Mesma rede, 3 sementes: F2 igual, mas **alarme falso de 1 a 5** |
| `atalho` | A rede olha a chama ou o formato? | Recall nas 297 fotos: 95,3% / 96,6% / 100% |
| `custo` | Quanto custa rodar? | Por imagem na CPU: ResNet18 ~34 ms, EfficientNet-B0 ~30–35 ms, DenseNet121 ~92–97 ms |

**Conclusão:** uma ou duas imagens de diferença não provam que uma rede é melhor; a EfficientNet-B0 foi escolhida pelo custo.

## Registro do uso de IA (como está no README do benchmark)

Ideia: professor. Escolha das campanhas e da rede: autoras. Código (`rodar.py`, campanhas, scripts 11 a 13b, README): gerado pelo Claude, executado e conferido pelas autoras. Números dos relatórios vêm dos arquivos gerados, não foram digitados à mão.
