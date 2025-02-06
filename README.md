# AISearch
Potencial do serviço Azure AI Search

O Azure AI Search permite fazer buscas cognitivas de forma personalizada na nuvem. Para isso é necessário:

1) Ciar  2 recursos e uma conta de armazenamento:

- Azure AI Search (mecanismo de busca)
- Azure AI Service (recurso de inteligencia artificial)
- Azure Storage Account (conta de armazenamento de informações)
 
2) Em armazenamento de dados criar un novo container
3) Fazer o upload do arquivo contendo a informação que tem o banco de dados para o AI Search
4) No Azure AI Search criado importar os dados. Na fonte de dados selecionar armazenamento de blob do Azure e colocar o nome da fonte de dados. Na Cadeia de conexão escolher uma conexão existente (selecionar a conta de armazenamento e o nome do conteiner).
5) Na seção anexar serviços de IA selecionar o recurso de serviços de IA do Azure. Na seção de importar dados alterar o nome do Skillset e habilitar OCR. Alterar o nivel de granularidade de enriquecimento para Paginas e selecionar as habilidades cognitivas que o recurso de AI utilizara e que sejam de interesse para o banco de busca (p. ex. habilidaees cognitivas de texto: extrair nomes de localização, extrair frases-chave, detectar sentimento. Habilidades cognitivas de imagem: gerar tags a partir de imagens, gerar legendas a partir de imagens). Na seção enriquecmentos em salvar enriquecimentos em um armazenamento de conhecimento selecionar a cadeia de conexão da conta de armazenamento (banco de dados existente) e em projeções de arquivo do Azure escolher: projeções de imagem, DOcumentos, páginas, frases-chave, entidade, detalhes e referencias da imagem.
6) Em personalizar índice de destino alterar o nome do índice e selecionar filtrável para todos os campos que já estão selecionados por padrão.
7) Criar um indexador (colocar o nome), programar como Uma vez e em opções avançadas certificar que  a opção Base-64 Encode Keys esteja selecionada. Fazendo isso o indexador ira a extrair os dados do documentos e conteudo da fonde de dados, executará o conjunto de habiliadaes cognitivas para gerar campos mais enriquecidos e mapeará os campos extraidos para o indice.
8) Retornar à pagina com o recurso do Azure AI Search e clicar em Explorador de pesquisa. Com o indice selecinando o arquivo com a fonte de dados ir no editor de consulta (linha pesquisa) e escrever os comandos para fazer a busca usando o formato search=enriquecimento 'Nome'. Por exemplo: Caso queira buscar no banco de dados as informações provenientes da cidade de Chicago, escrever: search=locations 'Chicago' e clicar em pesquisar.


O uso deste conjunto de ferramentas é possível extrair de uma enorme base de dados: palavras chaves, sentimentos, etc de uma forma rapida, precisa e automatizada, usando habilidades cognitivas. Isto pode ser muito útil para atendimento ao cliente, na pesquisa de documentos ou até mesmo no e-commerce.












