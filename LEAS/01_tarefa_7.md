# LEAS · Tarefa 7: LLMs reproduzem os selos oficiais de um artefato?

| Campo | Registro |
|---|---|
| Disciplina | LEAS |
| Data | Repositório com commits de 28/09/2026 |
| Situação | **Entregue** (com lacunas apontadas na revisão de 23/11/2026) |
| Repositório | `mariadlribeiro/artefatos-atividade-7` (privado) |

## Enunciado (resumo; texto completo em `enunciados/`)

Escolher um artefato do SBSeg ou SBRC (https://doc-artefatos.github.io), identificar os selos oficiais e as instruções de avaliação da edição, e usar **pelo menos 3 LLMs de 3 provedores** para fazer duas avaliações: **analítica** (selos F e R com evidências) e **por execução**. Registrar prompts, resultados e evidências, verificar as evidências no artefato, montar tabela comparativa e fluxograma, e concluir sobre a consistência das LLMs com a avaliação oficial.

## O que foi feito

- **Artefato:** IoT-ID, https://github.com/GT-IoTEdu/sbrc26_fingerprint (SBRC 2026, Salão de Ferramentas).
- **Selos oficiais:** D, F, S e R.
- **LLMs:** Claude (Anthropic), Grok (xAI) e Gemini (Google). Uma rodada com o DeepSeek foi excluída porque ele avaliou outro artefato.
- **Prompt padronizado** igual para as três (`docs/PROMPT_PADRONIZADO.md`).

## Resultado registrado

| LLM | F | R | Observação |
|---|---|---|---|
| Claude | Execução parcial | Reprodução parcial, com divergências (TCL e Xiaomi) | Recalculou hashes |
| Grok | Atende, com limitações | Atende, com limitações | Apoiou-se nos resultados dos próprios autores |
| Gemini | Não verificável | Não verificável | Não conseguiu acessar o repositório (falha de rede) |

## Lacunas encontradas na revisão (23/11/2026)

- Versões exatas dos modelos, modo de raciocínio e datas não foram registrados.
- A metodologia citava as instruções do **SBSeg 2024**; o artefato é do **SBRC 2026**, que tem página própria (https://doc-artefatos.github.io/sbrc2026/revinstrucoes.html).
- Respostas brutas das LLMs precisavam ser salvas no repositório.
