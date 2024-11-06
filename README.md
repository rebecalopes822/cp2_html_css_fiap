# O Poder da Astronomia

## Descrição do Projeto

**O Poder da Astronomia** é um site criado para explorar e apresentar conceitos relacionados à astronomia. O site é estruturado para fornecer informações sobre a astronomia, incluindo definições, importância, e diferenças com a astrologia, além de destacar figuras históricas importantes na área.

## Contexto do Desenvolvimento

Este projeto foi desenvolvido no início do período da faculdade, durante o aprendizado dos conceitos básicos de desenvolvimento web. Foi uma oportunidade para praticar habilidades em HTML e CSS, e para criar um site com uma apresentação visual impactante e informativa.

## Estrutura do Projeto

O site é composto por:

- **Parte Superior**: 
  - **Imagem Principal**: Exibe uma imagem relevante com um texto sobre a astronomia.
  - **Título**: Adiciona um título chamativo sobre o poder da astronomia.
- **Parte Inferior**:
  - **Imagens e Textos**: Exibe várias seções com imagens e textos sobre conceitos e importância da astronomia, a história de Nicolau Copérnico e a diferença entre astronomia e astrologia.

## Tecnologias Utilizadas

- **HTML**: Estrutura do conteúdo da página.
- **CSS**: Estilo e layout do site, com flexbox para a organização das partes superiores e inferiores e design responsivo.
- **Imagens**: Imagens ilustrativas relacionadas ao tema da astronomia.

## Recursos

- **CSS Inline**: Estilo incluído diretamente no arquivo HTML para controle do layout e design.
- **Imagens**: Imagens usadas para ilustrar conceitos e tornar o conteúdo visualmente atraente.

## Responsividade

O design do site é responsivo, utilizando flexbox para garantir que a apresentação se ajuste a diferentes tamanhos de tela. A estrutura muda de uma visualização em coluna para uma visualização em linha em telas maiores (a partir de 600px).

## Observações

- **Estilos Inline**: O CSS está incluído diretamente no arquivo HTML. Para uma melhor organização, é recomendado mover os estilos para um arquivo CSS externo.
- **Correções e Atualizações**: O código pode ser aprimorado para melhorar a manutenção e a organização, incluindo a correção do atributo `meta name` duplicado e a melhoria da acessibilidade e semântica.

## Como Executar

Para visualizar o site, abra o arquivo `index.html` em um navegador web. Certifique-se de que as imagens estão carregando corretamente a partir dos links fornecidos.

## Conclusão

**O Poder da Astronomia** é um projeto de site que demonstra a capacidade de criar uma apresentação visualmente atraente e informativa sobre a astronomia. É um exemplo inicial de aplicação prática de conceitos de desenvolvimento web, refletindo o início da jornada de aprendizado no desenvolvimento de sites.



TODO-APP
Descrição do Projeto
O TODO-APP é uma aplicação simples de gerenciamento de tarefas, desenvolvida utilizando Flask como framework para a criação de uma API RESTful, com persistência de dados em um banco de dados Oracle. O projeto foi containerizado utilizando Docker e Docker Compose para simplificar a implantação e o gerenciamento dos serviços.

Objetivos
Implementar uma API para gerenciar tarefas com operações CRUD (Create, Read, Update, Delete).
Utilizar persistência de dados com OracleDB.
Garantir a facilidade de implantação e escalabilidade com Docker e Docker Compose.
Estrutura do Projeto
plaintext
Copiar código
TODO-APP/
├── api/
│   ├── app.py                # Código principal da API
│   └── requirements.txt      # Dependências do projeto
├── docker-compose.yml        # Configuração de serviços Docker
├── Dockerfile                # Configuração do container da aplicação
└── README.md                 # Este arquivo README
Pré-requisitos
Docker
Docker Compose
Configuração e Execução
Clone o repositório:

bash
Copiar código
git clone <link-do-repositorio>
cd TODO-APP
Configuração do Docker Compose: Certifique-se de que o arquivo docker-compose.yml está configurado corretamente, incluindo o endereço do banco de dados Oracle.

Inicie a aplicação com Docker Compose:

bash
Copiar código
docker-compose up -d
Esse comando irá construir as imagens necessárias e iniciar os containers em background. A API estará disponível em http://localhost:5000.

Testando a API:

Criar uma nova tarefa:

bash
Copiar código
curl -X POST http://localhost:5000/tasks -H "Content-Type: application/json" -d '{"title": "Minha Tarefa", "description": "Descrição da tarefa"}'
Listar todas as tarefas:

bash
Copiar código
curl http://localhost:5000/tasks
Atualizar uma tarefa existente:

bash
Copiar código
curl -X PUT http://localhost:5000/tasks/1 -H "Content-Type: application/json" -d '{"title": "Novo Título", "description": "Nova descrição"}'
Deletar uma tarefa:

bash
Copiar código
curl -X DELETE http://localhost:5000/tasks/1
Arquitetura do Projeto
A aplicação utiliza uma arquitetura de microserviços, com os seguintes componentes:

API (Flask): Responsável pelo gerenciamento das tarefas com operações CRUD.
Banco de Dados Oracle: Usado para armazenar os dados das tarefas de forma persistente.
Docker e Docker Compose: Para orquestrar e gerenciar os containers da aplicação e do banco de dados.
Notas Técnicas
O arquivo Dockerfile foi configurado com uma imagem Python Slim para melhorar a eficiência e reduzir o tamanho do container.
Docker Compose está configurado para mapear a porta 5000 do container para a porta 5000 do host.
As variáveis de ambiente são definidas no docker-compose.yml para facilitar a configuração do banco de dados.
