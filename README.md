# 🍽️ Restaurant Management API

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Java](https://img.shields.io/badge/Java-21-orange)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen)
![H2](https://img.shields.io/badge/H2-Database-blue)

Backend REST API para um sistema de gerenciamento de restaurantes compartilhado. Desenvolvido como parte do **Tech Challenge (Pós-Graduação)** utilizando **Spring Boot, JDBC (JdbcTemplate), H2 Database e Lombok**.

---

## 📌 Requisitos do Projeto (Tech Challenge)

O projeto cumpre integralmente os critérios técnicos exigidos:

- [x] **CRUD de Usuários**: Gestão completa de perfis.
- [x] **Segurança de Dados**: Endpoints distintos para atualização de dados cadastrais e alteração de senha.
- [x] **Rastreabilidade**: Controle automático da data da última atualização (`lastUpdateDate`).
- [x] **Busca Avançada**: Filtro de usuários por nome.
- [x] **Integridade**: Validação de e-mail único.
- [x] **Autenticação**: Serviço de validação de login.
- [x] **Padronização API**: Versionamento `/v1` e tratamento de erros via **RFC 7807 (ProblemDetail)**.
- [x] **Documentação**: Swagger UI integrada e Postman Collection inclusa.

---

## 🏗️ Arquitetura

A aplicação segue o padrão de camadas para garantir a separação de responsabilidades e facilidade de manutenção:


* **Controller**: Exposição dos endpoints REST e manipulação de requisições HTTP.
* **Service**: Camada de lógica de negócio e validações.
* **Repository**: Persistência de dados utilizando `JdbcTemplate` para manipulação de SQL.
* **DTOs**: Objetos de transferência de dados para requisições e respostas.
* **RowMapper**: Mapeamento manual entre o `ResultSet` do SQL e os Objetos de Domínio.

---

## 🔗 Endpoints da API (v1)

A URL base da API é: `http://localhost:8080/api/v1`

### Usuários
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `POST` | `/users` | Cadastro de novo usuário |
| `GET` | `/users?name={nome}` | Lista usuários com filtro opcional por nome |
| `PUT` | `/users/{id}` | Atualiza dados (Exceto senha) |
| `PATCH` | `/users/{id}/password` | Altera a senha (Endpoint exclusivo) |
| `DELETE` | `/users/{id}` | Remove um usuário |

### Autenticação
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `POST` | `/auth/login` | Validação de credenciais de acesso |

---

## 🛠️ Tecnologias e Dependências

* **Java 21**
* **Spring Boot 3.x**
* **Spring JDBC (JdbcTemplate)**: Para interação direta com o banco via SQL.
* **H2 Database**: Banco de dados em memória para desenvolvimento e testes.
* **Lombok**: Redução de código boilerplate (Getters/Setters).
* **SpringDoc OpenAPI**: Geração automática da documentação Swagger.

---