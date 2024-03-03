# LAB4 IA-900
#### PROJETO PARA CERTIFICAÇÃO MICROSOFT IA-900 DA DIO

![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white)

> ## Dados sobre o projeto:

- _Crie um novo repositório no github com um nome a sua preferência;_
- _Crie um um arquivo readme.md descrevendo o passo a passo para se configurar uma pesquisa, assim como seus insights, possibilidades de ferramentas que se beneficiam com esse tipo de ferramenta e aprendizados adquiridos durante o processo;_
- _Compartilhe conosco o link desse repositório através do botão 'entregar projeto'._


##
> ### Configurações:
##
  - Criar um recurso de Pesquisa de IA do Azure
  - Criar uma conta de armazenamento
  - Carregar documentos no Armazenamento do Azure
  - Indexar os documentos
      - No portal do Azure, navegue até seu recurso de Pesquisa de IA do Azure. Na página Visão geral, selecione Importar dados.
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/b0e0548e-8f10-4d89-9c42-55ec1612a2ab)
      - Na página Conectar aos seus dados, na lista Fonte de Dados, selecione Armazenamento de Blobs do Azure. Conclua os detalhes do armazenamento de dados com os seguintes valores:
         - Fonte de dados: Armazenamento de Blobs do Azure
         - Nome da fonte de dados: coffee-customer-data
         - Dados a serem extraídos: conteúdo e metadados
         - Modo de análise: Padrão
         - Cadeia de conexão: *Selecione Escolher uma conexão existente. Selecione sua conta de armazenamento, selecione o contêiner de revisões de café e clique em Selecionar.
         - Autenticação de identidade gerenciada: Nenhuma
         - Nome do contêiner: essa configuração é preenchida automaticamente depois que você escolhe uma conexão existente.
         - Pasta Blob: deixe isso em branco.
         - Descrição: Comentários a Fourth Coffee shops.
          ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/4fa26183-438e-4db9-8241-10796e4ae12b)
        - Selecione Avançar: Adicionar habilidades cognitivas (Opcional).
       
        - Na seção Anexar Serviços Cognitivos, selecione seu recurso de serviços de IA do Azure.
          ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/09aab7b8-1d9c-40e0-b845-ecfd1bb68657)

        - Na seção Adicionar enriquecimentos:
          - Altere o nome do Skillset para coffee-skillset.
          - Marque a caixa de seleção Habilitar OCR e mesclar todo merged_content texto em campo
          - Verifique se o campo Dados de origem está definido como merged_content.
          - Altere o nível de granularidade de enriquecimento para Páginas (blocos de 5000 caracteres).
          - Não selecione Habilitar enriquecimento incremental
          - Selecione os seguintes campos enriquecidos:
          - Habilidade Cognitiva	Parâmetro	Nome do campo
            
            |              Extrair              | nomes de locais	 | 	     Locais      |
            | ----------------------------------|------------------|-------------------|
            |Extrair frases-chave	 	            |                  |    Frases-chave   |
            |Detectar sentimento	 	            |                  |    sentimento     |
            |Gerar tags a partir de imagens	    | 	               |    imageTags      |
            |Gerar legendas a partir de imagens	| 	               |    imageCaption   |
   
          - Em Salvar enriquecimentos em um repositório de conhecimento, selecione:
             - Projeções de imagens
             - Documentos
             - Páginas
             - Frases-chave
             - Entidades
             - Detalhes da imagem
             - Referências de imagens
   
          - Selecione Projeções de blob do Azure: Documento. Uma configuração para Nome do contêiner com as exibições preenchidas automaticamente pelo contêiner do repositório de conhecimento. Não altere o nome do contêiner.

          - Selecione Avançar: Personalizar índice de destino. Altere o nome do índice para coffee-index.

          - Verifique se a chave está definida como metadata_storage_path. Deixe o nome do Sugeridor em branco e o modo de Pesquisa preenchido automaticamente.

          - Revise as configurações padrão dos campos de índice. Selecione filtrável para todos os campos que já estão selecionados por padrão.
               
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/2de8cb35-5733-498a-8855-1754468cedb8)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/cb88c445-6737-4e9d-b7fe-6346545944cf)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/209965cf-094e-4997-b129-41dcfa33bd55)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/3b20aefc-24bc-430f-9fdc-ab641b13ed41)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/d86dbcca-23d3-4cf8-b9e0-fde04fe86c0b)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/2c05656a-7716-493f-b26b-833d4fdbc673)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/8608b348-9b52-4c91-b8de-3ecf2e54ee96)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/d2d6062c-0ec3-4367-b725-5a06e68d85ce)
        ![image](https://github.com/vinicius-campelo/lab4-ia900/assets/74797865/6c7ca1e6-0c5c-4a0c-831e-9ffcc9c0350b)










  - Consultar o índice
  - Revisar o repositório de conhecimento

> ## Referências:

 - [Explore Speech Studio](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/09-speech.html)
 - [Analyze text with Language Studio](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/06-text-analysis.html)
