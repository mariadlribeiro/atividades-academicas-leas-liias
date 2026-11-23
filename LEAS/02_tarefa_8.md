# LEAS · Tarefa 8: as avaliações da T7 são robustas?

| Campo | Registro |
|---|---|
| Disciplina | LEAS |
| Data | Iniciada em 23/11/2026 |
| Situação | **Em andamento** |
| Repositório | `mariadlribeiro/artefatos-atividade-7`, branch `tarefa-8` |

## Enunciado (resumo; texto completo em `enunciados/`)

Repetir a avaliação da T7 com **o mesmo artefato, as mesmas instruções e, de preferência, as mesmas LLMs**, introduzindo variações controladas: outra versão do modelo, maior esforço de raciocínio (inclusive o máximo) ou outra variação justificada. Registrar configurações, prompts, resultados e evidências; verificar as evidências no artefato; comparar T7 × T8; atualizar o fluxograma; concluir sobre robustez e sensibilidade.

## O que já foi feito

- **Protocolo** (`docs/T8/PROTOCOLO_T8.md`): variações V0 (linha de base T7), V1 (esforço máximo), V2 (versão nova), V3 (as duas), V4 opcional (prompt com as instruções oficiais do SBRC 2026). Uma variável por vez.
- **Prompts** (`docs/T8/PROMPTS_T8.md`): P1 = prompt da T7 sem alterações; P2 = P1 + instruções oficiais.
- **Fichas de resultado, tabela comparativa T7 × T8, fluxograma em Mermaid e rascunho da conclusão.**
- **Verificação direta do artefato** (`docs/T8/VERIFICACAO_EVIDENCIAS.md`, `scripts/recompute_hashes.py`), commit `167f487`:
  - 22/22 execuções são internamente consistentes (SHA-256 da string canônica = hash armazenado);
  - com a política registrada (`stable`), só **11/22** são reconstruídas;
  - as 6 do TCL só reproduzem com `rich`; as 5 do Xiaomi e 2 do IP `.100` não reproduzem com nenhuma política.
- **Rodadas do Claude:** T8-C-01 (Claude Opus 5.5, esforço padrão) e T8-C-02 (Claude Opus 5.5, esforço máximo), cada uma num agente novo, sem histórico, com o mesmo prompt da T7. O contraste entre as duas isola o efeito do esforço.

## Pendências

- Concluir a análise das rodadas T8-C-01 e T8-C-02 e preencher as fichas.
- Rodadas das outras LLMs. O escopo final (quais LLMs foram repetidas e por quê) está registrado no protocolo; conferir antes da entrega.
- Recuperar as versões usadas na T7 (`docs/CONFIG_T7.md`); se não houver registro, declarar "não registrado na T7".
- Tabela final, fluxograma atualizado, conclusão e README.
- Merge da branch `tarefa-8`.
