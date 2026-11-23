# Glossário

Termos usados nos trabalhos, explicados de forma curta.

## Dataset e treino (LIAA)

| Termo | O que é |
|---|---|
| **SHA-256** | "Impressão digital" de um arquivo. Arquivos idênticos têm o mesmo SHA-256. Usado para achar cópias exatas e provar que os originais não mudaram. |
| **dHash** | Hash de imagem que muda pouco quando a imagem muda pouco. Duas fotos com distância ≤ 6 foram tratadas como quase iguais. |
| **Grupo de duplicatas** | Conjunto de imagens iguais ou quase iguais. Fica inteiro num só conjunto (treino, validação ou teste) para evitar vazamento. |
| **Vazamento de dados** | Quando uma imagem (ou quase a mesma) está no treino e no teste: a rede "lembra" a resposta e o resultado fica otimista demais. |
| **CLIP** | Modelo que compara imagem e texto. Usado só para **sugerir** rótulos; a decisão foi humana. |
| **Auditoria cega** | Revisão em que a sugestão da IA fica escondida, para medir quanto a IA acerta sem influenciar quem revisa. |
| **k-centros** | Algoritmo que escolhe, entre muitas imagens, as mais diferentes entre si. Evita pegar vários quadros do mesmo vídeo. |
| **WeightedRandomSampler** | Sorteio com pesos no treino: equilibra as classes sem apagar nem copiar imagens. |
| **Aumento de dados** | Variações aleatórias das imagens de treino (girar, recortar, mudar brilho) para a rede generalizar melhor. |
| **Transferência de aprendizado** | Começar de uma rede já treinada no ImageNet e ajustá-la para fogo / sem fogo. |
| **ResNet18, DenseNet121, EfficientNet-B0** | As três redes convolucionais comparadas. A EfficientNet-B0 é a mais leve das três. |
| **Recall de fogo** | De todas as fotos com fogo, quantas a rede acertou. Fogo perdido = falso negativo. |
| **Precisão** | De todas as vezes que a rede disse "fogo", quantas eram fogo. Alarme falso = falso positivo. |
| **F2** | Métrica que junta recall e precisão dando **mais peso ao recall**: perder um incêndio custa mais que um alarme falso. |
| **Limiar calibrado** | Probabilidade a partir da qual a rede diz "fogo". Escolhido na validação para maximizar o F2. |
| **Validação saturada** | Quando todas as redes acertam quase tudo na validação (99,5–99,8%) e ela não serve mais para separar uma da outra. |
| **Atalho (shortcut learning)** | Quando a rede acerta por uma pista errada (por exemplo, o formato da foto) em vez de olhar para o que importa (a chama). |
| **Teste de atalho** | 297 fotos de floresta quadradas e pequenas, com e sem fogo: se a rede usasse o formato, o recall despencaria. |
| **Semente** | Número que fixa o acaso do treino. Mudar a semente mostra quanto o resultado varia só por acaso. |
| **SLIC** | Segmentação da imagem em superpixels (regiões parecidas). Usado nos experimentos anteriores. |
| **Grad-CAM** | Mapa de calor que mostra onde a rede "olhou" para decidir. |

## Avaliação de artefatos (LEAS)

| Termo | O que é |
|---|---|
| **Artefato** | O que acompanha um artigo científico: código, dados, scripts, instruções. |
| **Selo D (Disponível)** | O artefato está num repositório estável, com README completo. |
| **Selo F (Funcional)** | O artefato executa e o revisor consegue observar suas funcionalidades. |
| **Selo S (Sustentável)** | Código organizado, modular e legível. |
| **Selo R (Reprodutível)** | O revisor consegue reproduzir as principais afirmações do artigo. |
| **Avaliação analítica** | A LLM lê o artefato e decide os selos com base nas evidências. |
| **Avaliação por execução** | A LLM (ou a pessoa) roda o artefato para confirmar ou questionar a análise. |
| **Evidência D / C / A / E** | Documentação / código / resultado dos autores / execução independente. |
| **Esforço de raciocínio** | Quanto a LLM "pensa" antes de responder; algumas permitem escolher até o máximo. |
| **Benchmark parametrizável** | Experimentos descritos como campanhas em arquivos de parâmetros; quem usa escolhe qual rodar. |
