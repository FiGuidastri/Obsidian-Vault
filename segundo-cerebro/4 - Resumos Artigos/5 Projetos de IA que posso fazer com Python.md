Resumo do artigo que li no Towards Data Science, sobre projetos de IA para fazer com [[python]] 
[[artigos]]

## Projeto 1 - Otimização de Curriculo
1. Criar um curriculo em um arquivo markdown
2. Testar vários tipos de templates diferentes
3. Usar o GPT para reescrever o curriculo dinamicamente
4. Converter o arquivo markdown para HTML e depois para PDF usando as bibliotecas markdown e pdfkit.

**Bibliotecas:** openai, markdown, pdfkit
## Projeto 2 - Sumario de Vídeos do YouTube
1. Extraia o video ID do link do youtube
2. Use o IO para extrair a transcrição do video usando youtube-transcript-api
3. Experimente prompts diferentes do chatgpt para sumarizar a transcrição
4. Usar a API de Python da OpenAI para automatizar o processo

**Bibliotecas:** openai, youtube-transcript-api
## Projeto 3 - Organizar PDFs automaticamente
1. Ler o resumo(abstract) de cada artigo usando PyMuPDF
2. Usar a biblioteca sentence-transformers para traduzir o resumo em incorporações de texto e armazená-los em um Pandas DataFrame
3. Use o algoritmo de cluster favorito do sklearn para agrupar as incorporações
4. Crie pastas para cada cluster e mova os arquivos para a pasta apropriada

**Bibliotecas** PyMuPDF, sentence-transformers, pandas, sklearn

## Projeto 4 - Pesquisa Multimodal
1. Dado um PDF, divida-o em seções e extraia as imagens usando PyMuPDF
2. Use um modelo de incorporação multimodal (nomic-ai/nomic-embed-text-v1.5i) para representar os pedaços e imagens como vetores densos e armazená-los em um dataframe
3. Repita para todos os PDFs
4. Dada uma consulta de usuário, passe-a pelo mesmo modelo de incorporação usado para a base de conhecimento
5. Calcule a pontuação de similaridade de cosseno entre a incorporação de consulta e cada item na base de conhecimento
6. Retornar os resultados top k

