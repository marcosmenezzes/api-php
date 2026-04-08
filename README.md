# API PHP

Projeto de estudo em PHP com arquitetura organizada em camadas, utilizando **PDO + SQLite** para persistência de dados e **Docker** para facilitar a execução do ambiente.

O sistema implementa um CRUD simples de **produtos**, servindo como base para aprender conceitos de organização de backend com PHP puro.

## Tecnologias utilizadas

- PHP 8.2
- SQLite
- PDO
- Docker
- Docker Compose

## Estrutura do projeto


api-php/
├── src/
│   ├── controllers/
│   │   └── productController.php
│   ├── db/
│   │   └── sqlite.db
│   ├── models/
│   │   └── product.php
│   ├── repositories/
│   │   └── productRepository.php
│   ├── services/
│   │   └── productService.php
│   ├── views/
│   │   └── productView.php
│   └── server.php
├── Dockerfile
├── docker-compose.yaml
└── test.php
Organização das camadas
Model

Representa a entidade do sistema.

product.php: define o produto com:
id
name
stock
Repository

Responsável pelo acesso aos dados no banco SQLite.

productRepository.php:
busca todos os produtos
busca produto por ID
salva produto
atualiza produto
remove produto
Service

Camada de regra de negócio.

productService.php:
centraliza operações de CRUD
faz a ponte entre controller e repository
Controller

Responsável por coordenar as ações da aplicação.

productController.php:
lista produtos
cria produto
atualiza produto
remove produto
View

Responsável pela saída dos dados.

productView.php:
exibe os produtos em formato de texto
Funcionalidades atuais
Listagem de produtos
Cadastro de produtos
Atualização de produtos
Exclusão de produtos
Persistência em banco SQLite
Como executar com Docker
1. Clonar o repositório
git clone https://github.com/marcosmenezzes/api-php.git
cd api-php
2. Subir o container
docker compose up --build

A aplicação ficará disponível em:

http://localhost:8000
Como funciona a execução

O projeto usa a imagem php:8.2-cli, instala suporte a pdo e pdo_sqlite, copia os arquivos para o container e sobe um servidor embutido do PHP apontando para:

src/server.php
Teste rápido

Existe um arquivo test.php usado para testar o fluxo de CRUD de produtos, incluindo:

criação
listagem
atualização
exclusão
Observações
O arquivo server.php ainda está em fase inicial e indica a intenção de criar endpoints para:
GET
POST
PUT
DELETE

Ou seja, o projeto já possui a base estrutural de uma API, mas ainda pode evoluir para expor rotas HTTP completas.

Próximos passos sugeridos
Criar rotas HTTP reais no server.php
Retornar respostas em JSON
Implementar tratamento de erros
Adicionar validações
Separar configuração de ambiente
Criar documentação dos endpoints
Adicionar migrations ou script de criação da tabela products
Objetivo do projeto

Este projeto foi desenvolvido com foco em aprendizado, praticando:

organização de código em camadas
separação de responsabilidades
CRUD com PHP
persistência com SQLite
execução com Docker
Autor

Marcos Menezes
