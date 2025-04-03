# azure-ai-search
# Passo a passo para se configurar uma pesquisa com o Azure AI Search de forma resumida:

## 1. Criar recursos no Azure
### 1. Criar um Azure AI Search

- Acesse o Azure Portal e clique em + Criar um recurso.

- Pesquise por Azure AI Search e configure:

    - Grupo de recursos: Novo ou existente

    - Nome do serviço: Único

    - Localização: Região disponível (ex.: East US 2)

    - Plano: Básico

- Clique em Review + Create e depois Create.

### 2. Criar um Azure AI Services

- Volte para o Azure Portal e crie um recurso Azure AI Services.

- Configure com:

    - Mesmo grupo de recursos e região do Azure AI Search.

    - Plano: Standard S0.

- Clique em Review + Create e depois Create.

### 3. Criar um Storage Account

- No Azure Portal, clique em + Criar um recurso e pesquise por Storage Account.

- Configure:

    - Grupo de recursos: Mesmo dos anteriores.

    - Nome único.

    - Localização: Qualquer região disponível.

    - Desempenho: Standard.

    - Redundância: Locally Redundant Storage (LRS).

- Após criar, vá em Configurações → Configuração e habilite Blob anonymous access.

----------------------

## 2. Upload de documentos no Storage

- No Azure Storage, vá até Containers e crie um container chamado coffee-reviews com acesso público.

    - Baixe os arquivos de avaliação em https://aka.ms/mslearn-coffee-reviews.

    - Extraia os arquivos e faça o upload para o container.

------------------------

## 3. Criar e configurar o índice no Azure AI Search

- No Azure AI Search, vá em Import Data.

    - Conecte ao Azure Blob Storage e selecione o container coffee-reviews.

    - Habilite OCR e configure enriquecimentos:

        - Localizações, Frases-chave, Sentimento, Tags e legendas de imagens.

    - Salve os dados no Knowledge Store criando um container knowledge-store.

    - Nomeie o índice como coffee-index e marque os campos como filtráveis.

------------------------------

## 4. Criar e rodar o Indexador

- Nomeie o indexador como coffee-indexer.

- Defina a execução como Uma vez.

- Habilite Base-64 Encode Keys.

- Clique em Submit para rodar a indexação automaticamente.

- Acompanhe o status do indexador em Indexers no Azure AI Search.

---------------
## Depois disso será possível realizar consultas dentro do Azure AI Search:
![image](https://github.com/user-attachments/assets/96f5dcff-f073-442e-95dc-2d21c9234110)

![image](https://github.com/user-attachments/assets/e0fe6f63-fd95-42e5-8567-fcb70388171d)

![image](https://github.com/user-attachments/assets/241a3eeb-6ae1-488a-af0e-48c47bf36a75)

![image](https://github.com/user-attachments/assets/506cae42-e242-45f8-a399-606ded40f7ab)


------------
### Para mais detalhes é interessante consultar o site oficial da documentação do Azure AI Search:

https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html
