# Apresentação: dicas práticas de uso de IA e agentes

| Campo | Registro |
|---|---|
| Disciplina | A confirmar (LEAS ou LIAA) |
| Tipo | Individual, apresentada em aula |
| Entrega | Slides ou material da apresentação (arquivo ou link) |
| Prazo | A confirmar |
| Situação | **A fazer** |

## Enunciado

Cada aluno deverá preparar uma apresentação com dicas práticas de uso de IA e/ou agentes, a partir da própria experiência. O objetivo é compartilharmos experiências entre todos, trazendo coisas legais e úteis que os colegas possam aplicar no dia a dia, na pesquisa e no trabalho.

Sugestões de temas (escolha um ou combine alguns):

- Criação de vídeos, animações, imagens, narração e música com IA: roteiro, ferramentas e fluxo de produção.
- Agentes que controlam outros sistemas: navegador, e-mail, planilhas, Classroom, GitHub, servidores, dispositivos de IoT.
- Agentes acionados por Slack, WhatsApp, Telegram ou e-mail, incluindo relatos de uso de agentes em empresas.
- Agentes de programação (por exemplo, Claude Code, Codex, Cursor e Copilot): fluxos de trabalho, revisão de código, testes e publicação de sites.
- Automação de tarefas repetitivas com agentes, scripts e integrações (por exemplo, n8n, Zapier, MCP e APIs).
- Apoio à pesquisa acadêmica: busca e leitura de artigos, revisão de literatura, escrita em LaTeX/Overleaf, análise de dados e geração de gráficos.
- Engenharia de prompts e de contexto: instruções persistentes, skills, memória, templates e exemplos que fazem diferença nos resultados.
- Criação de apresentações, sites, documentos e relatórios com IA.
- Modelos locais e abertos (por exemplo, Ollama, LM Studio e Hugging Face): quando valem a pena e como usá-los.
- Cuidados e limites: alucinações, verificação dos resultados, privacidade, segurança, custos e uso ético.
- Experiências que deram errado e as lições aprendidas.

Sempre que possível, faça uma demonstração ao vivo ou mostre um exemplo real, indique as ferramentas utilizadas (com links) e destaque o que funcionou, o que não funcionou e quanto tempo ou esforço a IA economizou.

## Material real do semestre que pode virar a apresentação

Exemplos que já existem e podem ser mostrados ao vivo. Os itens "o que funcionou / não funcionou" vêm do que está registrado nos repositórios e nas conversas; **o tempo economizado precisa ser estimado por você**, porque não foi medido.

| Tema do enunciado | Exemplo real | O que funcionou | O que não funcionou / cuidado |
|---|---|---|---|
| Agentes de programação, publicação de sites | 13 etapas do dataset, treino, benchmark e site no GitHub Pages, gerados com o Claude e executados no seu computador | Scripts reprodutíveis com manifestos SHA-256; regras escritas no início ("nunca mexer nos originais") respeitadas do começo ao fim | Push rejeitado por repositório desatualizado; o agente às vezes perdeu a conexão com o computador |
| Engenharia de prompts e de contexto | As 6 regras do dataset; o "Histórico acadêmico" com prompts de continuidade (feito no ChatGPT) | Regras explícitas e um documento de contexto evitam repetir explicações a cada conversa | O histórico do ChatGPT trouxe a sigla "LIIAS" e dados a conferir: contexto também precisa ser verificado |
| IA com revisão humana | Páginas de revisão em HTML: o CLIP sugere, a pessoa decide; auditoria cega | A auditoria cega mede quanto a IA acerta sem influenciar quem revisa | Rótulos dados só por IA (400 fotos) ficaram como limitação declarada |
| Cuidados e limites: verificação | Teste de atalho (297 fotos) e campanha de sementes | Testar se a rede olha a chama ou o formato; mostrar que 1 a 5 alarmes falsos mudam só por acaso | Um número bom no teste não prova que o modelo aprendeu a coisa certa |
| Avaliação de artefatos com LLMs | Tarefas 7 e 8 da LEAS | Mesmo prompt para várias LLMs; verificação de cada evidência no artefato | LLMs diferentes deram selos diferentes; uma não acessou o repositório; uma aceitou os resultados dos autores sem reproduzir |
| Vídeos, imagens e narração com IA | Retrospectiva de 2 min; curta LEGO (Google Flow, Higgsfield/Seedance); legenda automática (Whisper) da apresentação | Personagens e cenários como imagens de referência mantêm a consistência; legenda automática com revisão dos termos técnicos | Geradores de vídeo inventam texto nas telas; créditos e acesso gratuito limitados; transcrição erra nomes técnicos |
| Apresentações e documentos com IA | Slides e roteiro da apresentação final, falas em PDF | Rascunho rápido, revisado a partir dos números reais do repositório | Layout pode quebrar ao apresentar (o título da capa sobrepôs o subtítulo no Meet) |

## Ferramentas usadas no semestre (com links)

- Claude: https://claude.ai · Claude Code: https://claude.com/claude-code
- ChatGPT: https://chatgpt.com
- Grok: https://grok.com · Gemini: https://gemini.google.com
- GitHub e GitHub Pages: https://github.com · https://pages.github.com
- Kaggle (datasets): https://www.kaggle.com
- PyTorch / torchvision: https://pytorch.org
- CLIP (OpenAI): https://github.com/openai/CLIP
- Whisper / faster-whisper: https://github.com/SYSTRAN/faster-whisper
- Google Flow: https://labs.google/flow · Higgsfield: https://higgsfield.ai
- FFmpeg: https://ffmpeg.org

## Próximos passos

1. Confirmar disciplina, prazo e tempo de apresentação.
2. Escolher o foco (sugestão: agentes de programação + verificação dos resultados, com os exemplos acima).
3. Estimar o tempo economizado em cada exemplo.
4. Montar os slides e preparar a demonstração ao vivo.
