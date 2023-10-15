# Todolist API

Este é um projeto de exemplo de uma API de ToDo List desenvolvida com Java e Spring Boot. A aplicação permite que os usuários criem, atualizem e obtenham tarefas de suas listas de afazeres. Este projeto foi desenvolvido durante o evento online da **Rocketseat**, que demonstrou o potencial da linguagem de programação Java com Spring Boot para o desenvolvimento de APIs robustas.

## Índice

- [Tecnologias](#tecnologias)
- [Instalação](#instalação)
- [Uso](#uso)
- [Autenticação](#autenticação)
- [Endpoints](#endpoints)
- [Exemplos de Requisições](#exemplos-de-requisições)

## Tecnologias

- Java
- Spring Boot
- Banco de Dados H2 (para desenvolvimento)
- Maven (gerenciamento de dependências)
- Lombok (criação de getters e setters)

## Instalação

1. Clone o repositório:

   ```bash
   git clone https://github.com/adrianmouzinho/spring-todolist.git
   ```

2. Navegue até o diretório do projeto:
   ```bash
   cd spring-todolist
   ```

3. Construa o projeto com Maven:
   ```bash
   mvn clean install
   ```

4. Execute a aplicação:
   ```bash
   mvn spring-boot:run
   ```

A API estará disponível em `http://localhost:8080`.

## Uso

Para usar a API, você precisará de um cliente REST, como o Postman ou o Insomnia, ou você pode integrá-la em um aplicativo front-end.

## Autenticação

Para criar uma tarefa, atualizar, listar e excluir tarefas, é necessário adicionar um cabeçalho de autenticação Basic Auth, passando o nome de usuário (username) e senha (password).

- **username:** nome do usuário
- **password:** senha

## Endpoints

- `POST /users/`: Cria uma nova usuário **(não precisa de autenticação)**.
- `GET /tasks/`: Obtém todas as tarefas de um usuário.
- `GET /tasks/{id}`: Obtém uma tarefa específica por ID.
- `POST /tasks/`: Cria uma nova tarefa.
- `PUT /tasks/{id}`: Atualiza uma tarefa existente.
- `DELETE /tasks/{id}`: Exclui uma tarefa por ID.

## Exemplos de Requisições

### Exemplo de requisição para criar um usuário:

```json
POST /users/

{
	"name": "Adrian Mouzinho",
	"username": "adrianmouz",
	"password": "123456"
}
```

### Exemplo de requisição para criar uma tarefa (é necessário autenticação):

```json
POST /tasks/

{
   "title": "Completar o projeto",
   "description": "Terminar o README em Markdown",
   "priority": "ALTA",
   "startAt": "2023-10-15T15:00:00",
   "endAt": "2023-10-15T20:00:00"
}
```

### Exemplo de requisição para listar todas as tarefas de um usuário (é necessário autenticação):

```json
GET /tasks/
```